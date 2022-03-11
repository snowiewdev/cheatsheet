## Big O Notation
- gives the complexity (time & space) in worst case, to quantify performance when input size becomes large
- n: size of the input

### Constant time: O(1)
- does not affect by the input size
- e.g. a += 1

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
- e.g. while-loop based on n input size, normal for-loop
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
