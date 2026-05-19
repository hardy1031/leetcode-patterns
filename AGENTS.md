# LeetCode Project

勉強用のLeetCode回答リポジトリ。

## フォルダ構成

```
LeetCode/
├── CLAUDE.md
├── questions/                          # グループ別フォルダ
│   └── {グループ名}/
│       ├── README.md                   # グループの説明・共通パターン
│       └── {番号}_{問題名}/
│           ├── answers.py              # 回答（複数のSolutionクラス）
│           ├── tests/
│           │   └── test.py             # pytest用テスト
│           └── docs/
│               └── note.md            # 気づき・考えたこと（短く）
└── README.md
```

## ルール
- 毎回プロジェクト開始時と、このファイルへ書き込みをする際は必ず `AGENTS.md` と `CLAUDE.md` の内容を確認し、1文字でも差分があれば整合するまでプロジェクトを開始しない
- note.mdは `.docs/principles.md` のフレームワークに従い型だけ作成し、内容は人間が書く
- answers.pyは中身は書かないが、Solutionクラスの型だけ作る
- 新しく問題フォルダを作るとき、tests/test.pyは`questions/1_two_sums/tests/test.py`か`questions/greedy_algorithm/121_best_time_to_buy_and_sell_stock/tests/test.py`をテンプレートにして短く書く
- tests/test.pyの先頭にはdocstringでExamples・Constraintsを記載する（`questions/greedy_algorithm/121_best_time_to_buy_and_sell_stock/tests/test.py`参照）
- note.mdの先頭には問題タイトルと問題文を記載する（`questions/238_product_of_array_except_self/docs/note.md`参照）

### 問題の追加
- `questions/{グループ名}/{番号}_{問題名}/` フォルダを作る
- グループに README.md がなければ作成する
- フォルダ構成は上記テンプレートに従う

### 回答 (answers.py)
- 問題ごとにABC（抽象基底クラス）をinterfaceとして定義する（例: `TwoSum`, `ContainsDuplicate`）
- interfaceには`@abstractmethod`でLeetCode準拠のメソッドシグネチャを定義する
- 各回答は `Solution1(TwoSum)`, `Solution2(TwoSum)`, ... のようにinterfaceを継承して定義する

### テスト (tests/test.py)
- pytestを使用
- `pytest.mark.parametrize` で全Solutionクラス × 全テストケースを網羅する
- テストケースはLeetCodeのExamplesを使う

### ノート (docs/note.md)
- criticalな気づきだけを極めて短く書く
- note.mdに書き込む際は内容を厳しめにチェックし、間違いがあれば必ず指摘する
- note.mdのセクション構成は `.docs/principles.md` の課題理解フレームワークに従う
