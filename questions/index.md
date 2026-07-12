# Questions Index

LLM向け: このファイルで全問題を把握し、各問題の詳細は `{pattern}/{number}_{name}/` 以下のファイルを参照。

## How to use (for LLM)
- Weekly review生成時: このindexを読む → `needs_review: true` の問題を優先 → 各`analysis.md`を読んでquizを生成
- 新問題追加時: このindexに行を追加する

## Pattern Folders

| Pattern | Tier | Description |
|---------|------|-------------|
| `stack/` | 1 | LIFO problems — matching, nesting, monotonic |
| `two_pointers/sliding_window/` | 1 | Array/string window problems |
| `hash_table/` | 1 | Frequency counting, complement lookup |
| `binary_search/` | 1 | Sorted/search-space problems |
| `bfs_dfs/` | 1 | Tree/graph traversal |
| `backtracking/` | 1 | Permutations, combinations, subsets |
| `dynamic_programming/` | 2 | 1D/2D DP, Kadane's |
| `heap_priority_queue/` | 2 | Top-K, scheduling |
| `topological_sort/` | 2 | Dependency ordering |
| `union_find/` | 2 | Connectivity problems |
| `trie/` | 2 | Prefix search |
| `monotonic_stack/` | 3 | Next greater/smaller element |
| `bit_manipulation/` | 3 | Bitwise tricks |
| `greedy/` | 3 | Locally optimal choices |
| `prefix_sums/` | 3 | Prefix/suffix product or sum |
| `math/` | 3 | GCD, number theory |

## Problems

| # | Problem | Pattern Folder | Difficulty | needs_review | Last Review |
|---|---------|---------------|------------|--------------|-------------|
| 1 | Two Sum | hash_table | Easy | true | May 27, 2026 |
| 121 | Best Time to Buy and Sell Stock | two_pointers/sliding_window/variable_size | Easy | true | May 27, 2026 |
| 153 | Find Minimum in Rotated Sorted Array | binary_search | Medium | true | May 27, 2026 |
| 217 | Contains Duplicate | hash_table | Easy | true | May 27, 2026 |
| 238 | Product of Array Except Self | prefix_sums | Medium | true | May 27, 2026 |
| 334 | Increasing Triplet Subsequence | greedy | Medium | true | May 18, 2026 |
| 845 | Longest Mountain in Array | two_pointers/opposite_direction | Medium | true | May 27, 2026 |
| 918 | Maximum Sum Circular Subarray | dynamic_programming | Medium | true | May 18, 2026 |
| 1071 | Greatest Common Divisor of Strings | math | Easy | true | May 18, 2026 |
| 36 | Valid Sudoku | hash_table | Medium | true | May 27, 2026 |
| 202 | Happy Number | hash_table | Easy | true | May 20, 2026 |
| 128 | Longest Consecutive Sequence | hash_table | Medium | true | May 21, 2026 |
| 3 | Longest Substring Without Repeating Characters | two_pointers/sliding_window/variable_size | Medium | true | May 22, 2026 |
| 567 | Permutation in String | two_pointers/sliding_window/fixed_size | Medium | true | May 22, 2026 |
| 424 | Longest Repeating Character Replacement | two_pointers/sliding_window/variable_size | Medium | true | May 22, 2026 |
| 125 | Valid Palindrome | two_pointers/opposite_direction | Easy | true | May 25, 2026 |
| 167 | Two Sum II | two_pointers/opposite_direction | Medium | true | May 25, 2026 |
| 15 | 3Sum | two_pointers/opposite_direction | Medium | true | May 25, 2026 |
| 16 | 3Sum Closest | two_pointers/opposite_direction | Medium | true | June 19, 2026 |
| 11 | Container With Most Water | two_pointers/opposite_direction | Medium | true | May 25, 2026 |
| 76 | Minimum Window Substring | two_pointers/sliding_window/variable_size | Hard | true | Jun 17, 2026 |
| 20 | Valid Parentheses | stack/basic | Easy | true | June 19, 2026 |
| 150 | Evaluate Reverse Polish Notation | stack/basic | Medium | true | June 19, 2026 |
| 739 | Daily Temperatures | stack/monotonic | Medium | true | Jun 22, 2026 |
| 496 | Next Greater Element I | stack/monotonic | Easy | true | Jun 22, 2026 |
| 1475 | Final Prices With a Special Discount | stack/monotonic | Easy | true | Jun 22, 2026 |
| 853 | Car Fleet | stack/monotonic | Medium | true | Jun 24, 2026 |
| 704 | Binary Search | binary_search | Easy | true | Jun 24, 2026 |
| 35 | Search Insert Position | binary_search | Easy | true | Jun 24, 2026 |
| 74 | Search a 2D Matrix | binary_search | Medium | true | Jun 24, 2026 |
| 875 | Koko Eating Bananas | binary_search/on_answer_space | Medium | true | Jun 24, 2026 |
| 1456 | Maximum Number of Vowels in a Substring | two_pointers/sliding_window/fixed_size | Medium | true | Jun 25, 2026 |
| 206 | Reverse Linked List | linked_list/in_place_reversal | Easy | true | Jun 26, 2026 |
| 21 | Merge Two Sorted Lists | linked_list/dummy_node | Easy | true | Jun 27, 2026 |
| 92 | Reverse Linked List II | linked_list/in_place_reversal | Medium | true | June 29, 2026 |
| 141 | Linked List Cycle | linked_list/fast_slow_pointers | Easy | true | June 29, 2026 |
| 143 | Reorder List | linked_list/fast_slow_pointers | Medium | true | June 29, 2026 |
| 876 | Middle of the Linked List | linked_list/fast_slow_pointers | Easy | true | June 29, 2026 |
| 19 | Remove Nth Node From End of List | linked_list/two_pointers | Medium | true | June 30, 2026 |
| 203 | Remove Linked List Elements | linked_list/dummy_node | Easy | true | June 30, 2026 |
| 61 | Rotate List | linked_list/two_pointers | Medium | true | June 30, 2026 |
| 82 | Remove Duplicates from Sorted List II | linked_list/dummy_node | Medium | true | June 30, 2026 |
| 138 | Copy List with Random Pointer | hash_map | Medium | true | July 1, 2026 |
| 2 | Add Two Numbers | linked_list/dummy_node | Medium | true | July 1, 2026 |
| 287 | Find the Duplicate Number | linked_list/fast_slow_pointers | Medium | true | July 2, 2026 |
| 142 | Linked List Cycle II | linked_list/fast_slow_pointers/floyd_cycle_detection | Medium | true | July 3, 2026 |
| 146 | LRU Cache | linked_list/doubly_linked_list | Medium | true | July 3, 2026 |
| 226 | Invert Binary Tree | tree/dfs/bottom_up/basic | Easy | true | July 3, 2026 |
| 104 | Maximum Depth of Binary Tree | tree/dfs/bottom_up/basic | Easy | true | July 3, 2026 |
| 543 | Diameter of Binary Tree | tree/dfs/bottom_up/retval_not_answer | Easy | true | July 3, 2026 |
| 110 | Balanced Binary Tree | tree/dfs/bottom_up/retval_not_answer | Easy | true | July 4, 2026 |
| 100 | Same Tree | tree/dfs/bottom_up/basic | Easy | true | July 4, 2026 |
| 572 | Subtree of Another Tree | tree/dfs/bottom_up/basic | Easy | true | July 4, 2026 |
| 235 | Lowest Common Ancestor of a BST | tree/bst | Medium | true | July 5, 2026 |
| 102 | Binary Tree Level Order Traversal | tree/bfs/level_batching | Medium | true | July 5, 2026 |
| 199 | Binary Tree Right Side View | tree/bfs/level_batching | Medium | true | July 5, 2026 |
| 1448 | Count Good Nodes in Binary Tree | tree/dfs/top_down | Medium | true | July 7, 2026 |
| 98 | Validate Binary Search Tree | tree/dfs/top_down | Medium | true | July 7, 2026 |
| 230 | Kth Smallest Element in a BST | tree/bst/in_order | Medium | true | July 8, 2026 |
| 530 | Minimum Absolute Difference in BST | tree/bst/in_order | Easy | true | July 8, 2026 |
| 538 | Convert BST to Greater Tree | tree/bst/in_order | Medium | true | July 8, 2026 |
| 105 | Construct Binary Tree from Preorder and Inorder Traversal | tree/construction | Medium | true | July 8, 2026 |
| 703 | Kth Largest Element in a Stream | heap_priority_queue | Easy | true | July 9, 2026 |
| 1046 | Last Stone Weight | heap_priority_queue | Easy | true | Jul 9, 2026 |
| 973 | K Closest Points to Origin | heap_priority_queue | Medium | true | Jul 11, 2026 |
| 621 | Task Scheduler | heap_priority_queue | Medium | true | Jul 11, 2026 |
