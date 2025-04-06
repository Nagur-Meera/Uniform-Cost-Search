# 🚀 Uniform Cost Search - Pathfinding Algorithm

## 📌 Problem Statement

Given a weighted graph represented as an **adjacency list**, the task is to find the **optimal (least-cost)** path between a **source node `s`** and a **target node `t`** using the **Uniform Cost Search (UCS)** algorithm.

> 📍 In this specific problem:  
> - Start Node (`s`) = A  
> - Goal Node (`t`) = F

---

## 🧠 Algorithm: Uniform Cost Search (UCS)

### ✅ Description:

Uniform Cost Search is an informed search algorithm that explores paths in order of their **cumulative cost from the start node**. It is essentially Dijkstra’s algorithm with the goal-check added during expansion.

It always selects the node with the **lowest path cost** and guarantees the **optimal solution**, provided all edge costs are non-negative.

### 🔽 Step-by-Step Procedure:

1. **Initialize** a priority queue with a tuple: `(cost = 0, node = start, path = [])`.
2. While the queue is **not empty**:
   - Dequeue the element with the **least total cost**.
   - If the current node is the **goal**, return the path and total cost.
   - Otherwise, mark the node as **visited**.
   - For each neighbor of the current node:
     - If the neighbor has not been visited:
       - Add it to the priority queue with the updated cost and path.
3. If the goal is not reachable, return `None`.



### 🛠 Data Structures Used:
- **Min Heap (Priority Queue)** – to fetch the node with the least cost efficiently.
- **Set** – to track visited nodes.

---

## 🗺 Sample Graph (Adjacency List):

```python
Graph = {
    "A": [("F", 14), ("C", 9), ("B", 7)],
    "B": [("A", 7), ("C", 10), ("D", 15)],
    "C": [("A", 9), ("F", 2), ("B", 10), ("D", 11)],
    "D": [("B", 15), ("C", 11), ("E", 6)],
    "E": [("F", 9), ("D", 6)],
    "F": [("A", 14), ("C", 2), ("E", 9)]
}
