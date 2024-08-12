# What is Trie? 
A Trie is a special form of a N-ary Tree. Typically, a trie is used to store strings. Each Trie node represents a string (a prefix). Each node might have several children nodes while the paths to different children nodes represent different characters. And the strings the child nodes represent will be the origin string represented by the node itself plus the character on the path. 
![[trie.png]]
# How to Implement a Trie? 
```ts
class TrieNode {
    val: string 
    isWord: boolean
    children: Map<string, TrieNode>
    constructor(val) {
        this.val = val 
        this.isWord = false
        this.children = new Map()
    }
}

class Trie {
    root: TrieNode
    
    constructor() {
        this.root = new TrieNode('')
        // console.log(this.root)
    }

    insert(word: string): void {
        let cur = this.root, val = ""
        for (const ch of word) {
            if(!cur.children.has(ch)) {
                val += ch
                cur.children.set(ch, new TrieNode(val))
            }
            cur = cur.children.get(ch)
        }
        cur.isWord = true 
        // console.log(this.root)
    }

    search(word: string): boolean {
        let cur = this.root 
        for (const ch of word) {
            if(!cur.children.has(ch)) {
                return false 
            }
            cur = cur.children.get(ch)
        }
        return cur.isWord
    }

    startsWith(prefix: string): boolean {
        let cur = this.root
        for (const ch of prefix) {
            if(!cur.children.has(ch)) {
                return false 
            }
            cur = cur.children.get(ch)
        }
        return true 
    }
}

/**
 * Your Trie object will be instantiated and called as such:
 * var obj = new Trie()
 * obj.insert(word)
 * var param_2 = obj.search(word)
 * var param_3 = obj.startsWith(prefix)
 */
```

