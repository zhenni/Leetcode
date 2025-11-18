# Python Algorithm

### Two Pointer (Opposite Direction)

```python
def two_pointers_opposite(arr):
    left, right = 0, len(arr) - 1
    while left < right:
        # Process current elements
        current = process(arr[left], arr[right])
        
        # Update pointers based on condition
        if condition(arr[left], arr[right]):
            left += 1
        else:
            right -= 1
```

### Same Direction

```python
def two_pointers_same(arr):
    slow, fast = 0, 0
    while fast < len(arr):
        # Process current elements
        current = process(arr[slow], arr[fast])
        
        # Update pointers based on condition
        if condition(arr[slow], arr[fast]):
            slow += 1
        
        # Fast pointer always moves forward
        fast += 1
```

### DFS in Graph

```python
def dfs(root, visited):
    for neighbor in get_neighbors(root):
        if neighbor in visited:
            continue
        visited.add(neighbor)
        dfs(neighbor, visited)
```

### DFS in Graph using Stack

```python
def dfs(root, visited):
    stack = [root]
    visited.add(root)

    while stack:
        node = stack.pop()
        for neighbor in get_neighbors(node):
            if neighbor in visited:
                continue
            visited.add(neighbor)
            stack.append(neighbor)
```

### DFS in Tree

```python
def dfs(root, target):
    if root is None:
        return None
    if root.val == target:
        return root
    left = dfs(root.left, target)
    if left is not None:
        return left
    return dfs(root.right, target)
```

### DFS in Tree using Stack

```python
def dfs_stack(root, target):
    if not root:
        return None
    stack = [root]
    while stack:
        node = stack.pop()
        # process node
        if node.right:
            stack.append(node.right)
        if node.left:
            stack.append(node.left)
```

### DFS Backtracing

```python
ans = []
def dfs(start_index, path, [...additional states]):
    if is_leaf(start_index):
        ans.append(path[:]) # add a copy of the path to the result
        return
    for edge in get_edges(start_index, [...additional states]):
        # prune if needed
        if not is_valid(edge):
            continue
        path.add(edge)
        if additional states:
            update(...additional states)
        dfs(start_index + len(edge), path, [...additional states])
        # revert(...additional states) if necessary e.g. permutations
        path.pop()

```

### DFS Backtracing Aggregation

```python
def dfs(start_index, [...additional states]):
    if is_leaf(start_index):
        return 1
    ans = initial_value
    for edge in get_edges(start_index, [...additional states]):
        if additional states: 
            update([...additional states])
        ans = aggregate(ans, dfs(start_index + len(edge), [...additional states]))
        if additional states: 
            revert([...additional states])
    return ans

```

### BFS on Graph

```python
def bfs(root):
    queue = deque([root])
    visited = set([root])
    while len(queue) > 0:
        node = queue.popleft()
        for neighbor in get_neighbors(node):
            if neighbor in visited:
                continue
            queue.append(neighbor)
            visited.add(neighbor)
```

### BFS on Tree

```python
def bfs(root):
    queue = deque([root])
    while len(queue) > 0:
        node = queue.popleft()
        for child in node.children:
            if is_goal(child):
                return FOUND(child)
            queue.append(child)
    return NOT_FOUND
```

### Prefix Tree

<pre class="language-python"><code class="lang-python"><strong>
</strong>class TrieNode:
    def __init__(self):
        self.children = {}
        self.isWord = False

# Build the trie
root = TrieNode()
for word in words:
    node = root
    for char in word:
        if char not in node.children:
            node.children[char] = TrieNode()
        node = node.children[char]
    node.isWord = True
</code></pre>

### Union-Find

```python
class UnionFind:
    def __init__(self):
        self.id = {}

    def find(self, x):
        y = self.id.get(x, x)
        if y != x:
            self.id[x] = y = self.find(y)
        return y

    def union(self, x, y):
        self.id[self.find(x)] = self.find(y)

```



### More Tree

**iterative (stack-based)** DFS for **preorder**, **inorder**, and **postorder** traversals.

#### 🌳 1️⃣ Preorder (Root → Left → Right)

```python
def preorder_traversal(root):
    if not root:
        return []

    stack = [root]
    result = []

    while stack:
        node = stack.pop()
        result.append(node.val)

        # Push right first so left is processed first
        if node.right:
            stack.append(node.right)
        if node.left:
            stack.append(node.left)

    return result
```

#### 🌿 2️⃣ Inorder (Left → Root → Right)

```python
def inorder_traversal(root):
    stack = []
    result = []
    node = root

    while stack or node:
        # Go left as far as possible
        while node:
            stack.append(node)
            node = node.left

        # Process node
        node = stack.pop()
        result.append(node.val)

        # Then go right
        node = node.right

    return result
```

#### 🌲 3️⃣ Postorder (Left → Right → Root)

🅰 Using Two Stacks (Simplest)

```python
def postorder_traversal(root):
    if not root:
        return []

    stack1 = [root]
    stack2 = []
    result = []

    while stack1:
        node = stack1.pop()
        stack2.append(node)

        if node.left:
            stack1.append(node.left)
        if node.right:
            stack1.append(node.right)

    # Reverse process order
    while stack2:
        result.append(stack2.pop().val)

    return result
```

🅱 Using One Stack (More Compact)

```python
def postorder_traversal_one_stack(root):
    result = []
    stack = []
    last_visited = None
    node = root

    while stack or node:
        if node:
            stack.append(node)
            node = node.left
        else:
            peek = stack[-1]
            # If right child exists and hasn't been visited, go there
            if peek.right and last_visited != peek.right:
                node = peek.right
            else:
                result.append(peek.val)
                last_visited = stack.pop()
    return result
```

***

#### 🧠 Unified DFS Recursion

```python
def dfs(node):
    if not node: return
    # preorder action
    dfs(node.left)
    # inorder action
    dfs(node.right)
    # postorder action
```

#### 🌳 Unified Stack-Based Template

```python
def dfs_traversal(root, order="inorder"):
    if not root:
        return []

    result = []
    stack = [(root, 0)]  # (node, state)
    # state meanings:
    # 0 = just entered (preorder moment)
    # 1 = left done (inorder moment)
    # 2 = right done (postorder moment)

    while stack:
        node, state = stack.pop()

        if node is None:
            continue

        if state == 0:
            # Preorder moment
            if order == "preorder":
                result.append(node.val)
            # Push states in reverse execution order
            stack.append((node, 1))          # revisit for inorder
            stack.append((node.left, 0))     # explore left next

        elif state == 1:
            # Inorder moment
            if order == "inorder":
                result.append(node.val)
            stack.append((node, 2))          # revisit for postorder
            stack.append((node.right, 0))    # explore right next

        else:  # state == 2
            # Postorder moment
            if order == "postorder":
                result.append(node.val)

    return result
```
