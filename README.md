# AVL Finger Tree

A robust implementation of an AVL Tree in Python, featuring advanced dynamic operations and finger tree mechanics. This project was developed as part of the Data Structures course at Tel Aviv University.

While standard AVL trees provide guaranteed O(log n) time complexity for basic dynamic operations, this implementation extends that functionality with advanced tree manipulations, including splitting, joining, and optimized searching using finger tree concepts.

## 🚀 Features

* **Standard BST Operations:** Efficient `insert`, `delete`, and `search` functionality with automatic AVL rebalancing.
* **Finger Search & Insert:** Optimized `finger_search` and `finger_insert` operations that begin traversal from the maximum node. This significantly improves performance when accessing or inserting elements close to the maximum value.
* **Tree Join:** The `join(tree2, key, val)` operation dynamically merges two AVL trees around a separating key, maintaining the AVL balance property.
* **Tree Split:** The `split(node)` operation divides an existing AVL tree into two separate valid AVL trees (keys smaller than the node, and keys larger than the node).
* **Array Conversion:** Includes an in-order traversal method to export the tree structure to a sorted Python list.

## ⏱️ Time Complexities

| Operation | Time Complexity | Description |
| :--- | :--- | :--- |
| `search(key)` | O(log n) | Standard top-down search. |
| `finger_search(key)` | O(log d) | Search starting from the max node, where d is the number of elements between the max and the target key. |
| `insert(key, val)` | O(log n) | Insertion with automatic height updates and rebalancing. |
| `finger_insert(key, val)` | O(log n) | Insertion starting from the max node. |
| `delete(node)` | O(log n) | Node removal with successor/predecessor replacement and rebalancing. |
| `join(tree2, key, val)`| O(|h1 - h2| + 1) | Merges two trees, where h1 and h2 are the heights of the respective trees. |
| `split(node)` | O(log n) | Splits the tree into two separate trees around the given node. |

## 🛠️ Implementation Details

* **Language:** Python 3.13
* **Virtual Leaves:** This implementation utilizes virtual nodes (nodes with `None` keys) for all leaves. This structural choice simplifies the implementation of tree rotations and rebalancing logic by ensuring every real node always has two children.
* **Balance Factor Tracking:** The tree actively calculates balance factors and tracks the number of `promote` cases (height changes) during AVL rebalancing for theoretical performance analysis.

## 👥 Authors
* Ofir Sher
* Roy Dolev
