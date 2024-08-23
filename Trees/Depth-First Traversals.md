Preorder Traversal and Postorder Traversal apply to general tree. 
Inorder Traversal only apply to binary tree. 

The following codes are for binary tree. 
# Pre Order Traversal 
```js
const preorderTraverse = (node, array) => {
	if (!node) return array;
	array.push(node.value);
	array = preorderTraverse(node.left, array);
	array = preorderTraverse(node.right, array);
	return array;
};
```

# In Order Traversal 
```js
const inorderTraverse = (node, array) => {
	if (!node) return array;
	array = inorderTraverse(node.left, array);
	array.push(node.value);
	array = inorderTraverse(node.right, array);
	return array;
};
```

# Post Order Traversal 
```js
const postorderTraverse = (node, array) => {
	if (!node) return array;
	array = postorderTraverse(node.left, array);
	array = postorderTraverse(node.right, array);
	array.push(node.value);
	return array;
};
```

Back to [[Tree]]
