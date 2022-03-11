## Big O Notation
- gives the complexity (time & space) in worst case, to quantify performance when input size becomes large
- constants can be eliminated when calculating big O time complexity
- n: size of the input

### Constant time: O(1)
- does not affect by the input size
- e.g. a += 1, append element in array

### Logarithmic Time: O(log(n))
- e.g. binary search with 2 pointers
```
let low = 0;
let high = n-1;
while (low<= high){
  let mid = (low + high) / 2;
  if (array[mid] == value) {
    return mid;
  }
  if (array[mid] < value) {
    low = mid + 1;
  } 
  if (array[mid] > value) {
    high = mid - 1;
  }
}
return -1; // value not found
```
```
O(log2(n)) = O(log(n))
```

### Linear Time: O(n)
- depends on size of n linearly
- e.g. while-loop based on n input size, normal for-loop, insertion/delete of array element(needs to shift whole array)
```
while (i<n) do { i+=1 }
O(f(n)) = O(n)
```

### Quadractic Time: O(n^2)
- e.g. nested 2d for-loop
```
f(n) = n*n = n^2, O(f(n*n)) = O(n^2)
```


## Linked List
- sequential list of nodes that holds data which poinst to other nodes also containing data
- head: first node of linked list
- tail: last node of linked list
- pointer: reference to another node
- node: an object containing data & pointer
```
A -> B -> C -> D -> NULL
```

### Single & Doubly Linked List
- single linked list: only holds reference to next node
- doubly linked list: holds reference to both next & previous node
- single adv: less memory, simple implementation, cons: cannot access previous element easily
- doubly adv: can traverse backwards, cons: takes 2x memory

### Big O
- Linked List Insertion: O(1)
- Linked List Removal: O(n)
- Linked List Search: O(n)

### Code example
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

### Stack
- one-ended linear data structure that haves 2 primary operation -- push & pop, and a top pointer
- examples: browser history forward & backward, undo mechanism in editor, check brackets in code editor [[{}]()]
- Push, Pop, Peek: O(1)
- Search: O(n)

### Queue
- linear data structure that haves 2 primary operation -- enqueue & dequeue 
- enqueue: add element to the back of the list, O(1)
- dequeue/polling: remove element fromt the top of the list, O(1)
- examples: line up in movie theatre, web server request(first come first serve)

### Priority Queue
- a normal queue but each element has a certain priority
- heap: tree-based data structure that satisfies heap invariant, the top-node is ordered with respect to its child nodes & all nodes in the heap
- min heap: from smallest to largest
- max heap: from largest to smallest
- all heaps must be tree **
- example of binary heap
```
      1
     / \
    2   3
   / \ / \
  4  5 4  7
```

### Hashtable
- constant time lookup & update through mapping from a key to a value
- e.g. object
