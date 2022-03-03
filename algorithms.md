## Linked List
Normal Array Insertion: O(n)

Linked List for Array Insertion: O(1)
A -> B -> C -> D -> NULL
```
class Node{
  constructor(val){
    this.val = val;
    this.next = null;
  }
}

const a = new Node('A');
const b = new Node('B');
const c = new Node('C');
const d = new Node('D');

a.next = b;
b.next = c;
c.next = d;

const printLinkedList = (head) => {
  let current = head;
  while (current != null) {
    console.log(current.val);
    current = current.next;
  }
}

printLinkedList(a);    // with show A, B, C, D
```
