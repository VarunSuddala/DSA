# Binary Tree Problems - Combined Code

```python
# 1. Boundary Nodes
def boundary(root):
    if root is None:
        return

    print(root.data, end=" ")

    def left_boundary(node):
        if node:
            if node.left or node.right:
                print(node.data, end=" ")
            if node.left:
                left_boundary(node.left)
            else:
                left_boundary(node.right)

    def leaves(node):
        if node:
            if node.left is None and node.right is None:
                print(node.data, end=" ")
            leaves(node.left)
            leaves(node.right)

    def right_boundary(node):
        if node:
            if node.right:
                right_boundary(node.right)
            else:
                right_boundary(node.left)

            if node.left or node.right:
                print(node.data, end=" ")

    left_boundary(root.left)
    leaves(root.left)
    leaves(root.right)
    right_boundary(root.right)


# 2. Left View
def left_view(root):
    if root is None:
        return

    q = [root]

    while q:
        n = len(q)

        for i in range(n):
            node = q.pop(0)

            if i == 0:
                print(node.data, end=" ")

            if node.left:
                q.append(node.left)

            if node.right:
                q.append(node.right)


# 3. Right View
def right_view(root):
    if root is None:
        return

    q = [root]

    while q:
        n = len(q)

        for i in range(n):
            node = q.pop(0)

            if i == n - 1:
                print(node.data, end=" ")

            if node.left:
                q.append(node.left)

            if node.right:
                q.append(node.right)


# 4. Lowest Common Ancestor (LCA)
def lca(root, p, q):
    if root is None:
        return None

    if root.data == p or root.data == q:
        return root

    left = lca(root.left, p, q)
    right = lca(root.right, p, q)

    if left and right:
        return root

    if left:
        return left

    return right


# 5. Root to Node Path
def find_path(root, target, path):
    if root is None:
        return False

    path.append(root.data)

    if root.data == target:
        return True

    if find_path(root.left, target, path):
        return True

    if find_path(root.right, target, path):
        return True

    path.pop()
    return False


# 6. Build Tree (Inorder + Preorder)
def build(preorder, inorder):
    if not preorder or not inorder:
        return None

    root = Node(preorder[0])

    index = inorder.index(preorder[0])

    root.left = build(
        preorder[1:index+1],
        inorder[:index]
    )

    root.right = build(
        preorder[index+1:],
        inorder[index+1:]
    )

    return root
