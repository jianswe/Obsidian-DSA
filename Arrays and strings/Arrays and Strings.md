![[Arrays and Strings BigO.png]]
## Arrays
They are fixed size, contiguous memory chunks 
* That means you cannot grow it 
* There is no "insertAt" or push or pop. Doesn't mean you can't write those though 

Technically, an array can't be resized. A dynamic array, or list, can be. 
In the context of algorithm problems, usually when people talk about arrays, they are referring to dynamic arrays. 

![[Array.png]]
### ArrayList
We use JavaScript Object to implement Array.  
```js
class ArrayList {
	constructor() {
		this.length = 0;
		this.data = {};
	}
	push(value) {
		this.data[this.length] = value;
		this.length++;
	}
	pop() {
		const ans = this.data[this.length - 1];
		delete this.data[this.length - 1];
		this.length--;
		return ans;
	}
	get(index) {
		return this.data[index];
	}
	delete(index) {
		const ans = this.data[index];
		this._collapseTo(index);
		return ans;
	}
	_collapseTo(index) {
		for (let i = index; i < this.length; i++) {
			this.data[i] = this.data[i + 1];
		}
		delete this.data[this.length - 1];
		this.length--;
	}
	serialize() {
		return this.data;
	}
}
```
## Strings 
Strings are implemented differently between languages. In Python and Java, they are immutable. In C++, they are mutable. 

Back to [[README]]