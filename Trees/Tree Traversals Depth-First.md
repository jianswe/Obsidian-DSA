![[Tree Traversals.png]]
Preorder Traversal and Postorder Traversal apply to general tree. 
Inorder Traversal only apply to binary tree. 

The following code is for binary tree. 
```js
const preorderTraverse = (node, array) => {
	if (!node) return array;
	array.push(node.value);
	array = preorderTraverse(node.left, array);
	array = preorderTraverse(node.right, array);
	return array;
};

const inorderTraverse = (node, array) => {
	if (!node) return array;
	array = inorderTraverse(node.left, array);
	array.push(node.value);
	array = inorderTraverse(node.right, array);
	return array;
};

const postorderTraverse = (node, array) => {
	if (!node) return array;
	array = postorderTraverse(node.left, array);
	array = postorderTraverse(node.right, array);
	array.push(node.value);
	return array;
};
```

### Pre Order Traversal 
```ts 
function walk(curr: BinaryNode<number> | null, path: number[]): number[] {
	if (!curr) {
		return path 
	}

	// pre
	path.push(curr.value)
	// recurse 
	walk(curr.left, path)
	walk(curr.right, path)

	return path
}

export default function pre_order_search(head: BinaryNode<number>): number[] {
	return walk(head, [])
}
```

Back to [[Tree]]
