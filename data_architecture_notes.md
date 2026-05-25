# Data Architecture Notes — LeetCode Study App

## 用語

- **スキーマ設計 / ER設計** → テーブル・カラム・リレーションを決める作業
- **データアーキテクチャ設計** → どのストレージ技術を使うかも含めた設計

---

## ストレージ選択

### 結論: PostgreSQL一本で完結する

| ストレージ | 判断 | 理由 |
|-----------|------|------|
| PostgreSQL | ✅ 採用 | リレーションがある、柔軟なクエリが必要 |
| S3 | ❌ 不要 | テキストはRDBのTEXT列で十分。S3は画像・動画・大容量ファイル向け |
| DynamoDB | ❌ 不要 | JOINが必要なユースケースには合わない |

### RDB vs DynamoDB の分かれ目

本質は「**データ同士にリレーション（関係）があるかどうか**」。

| 状況 | 向いてるDB |
|------|-----------|
| データ同士が関係し合っている | RDB (PostgreSQL) |
| データが独立していて1つのキーで完結する | DynamoDB |
| スキーマが頻繁に変わる | DynamoDB |
| 秒間数十万リクエストのスケールが必要 | DynamoDB |

DynamoDBはJOINができないため、関連データを取得するにはアプリ側でN回リクエストを繰り返すN+1問題が発生する。

### S3が必要になるとしたら

- ユーザーが画像・動画を添付できる機能を追加するとき
- それまではRDB一本でOK

---

## ER設計の骨格

```
users
├── id (PK)
└── email

questions
├── id (PK)
├── number          -- LeetCode問題番号
├── title
├── description     -- TEXT
├── examples        -- TEXT
├── constraints     -- TEXT
├── leetcode_url
└── neetcode_url

-- Layer 3: Pattern (M:N、1問に複数patternありえる)
patterns
├── id (PK)
├── name            -- "sliding_window", "two_pointers"
└── tier            -- 1/2/3

question_patterns   -- questionsとpatternsの中間テーブル
├── question_id (FK → questions.id)
└── pattern_id  (FK → patterns.id)

-- Layer 2 / Layer 1 も同様にM:N
algorithms          -- Binary Search, Kadane's, etc.
data_structures     -- HashMap, Array, etc.
question_algorithms
question_data_structures

-- Userごとの学習データ
personal_notes
├── id (PK)
├── user_id     (FK → users.id)
├── question_id (FK → questions.id)
└── content     -- TEXT

review_history
├── id (PK)
├── user_id     (FK → users.id)
├── question_id (FK → questions.id)
├── reviewed_at
├── needs_review  -- boolean
└── confidence    -- 1-5
```

---

## JOINメモ

複数テーブルを繋いで一度に取得するSQL。

```sql
-- needs_review=true の問題タイトルを取得
SELECT questions.title
FROM review_history
JOIN questions ON review_history.question_id = questions.id
WHERE review_history.needs_review = true
  AND review_history.user_id = 42;
```

### Syntax

```sql
FROM   A
JOIN   B  ON  A.fk = B.pk
```

- `FROM` は起点テーブル。AでもBでも結果は同じ（可読性の問題）
- `ON` の条件: `テーブル名.カラム名 = テーブル名.カラム名`

### analysisの扱い

`analyses` テーブルにTEXTとして持つより、`question_patterns` / `question_algorithms` / `question_data_structures` に正規化する方が「sliding_windowパターンの問題一覧」などのクエリが簡単に書ける。
