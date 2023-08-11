 # My-learning-journey.
## topics
<details>
  <summary>data struture</summary>

  <details>
    <summary>day 1</summary>
  <discription> 
    <h1> Learn about  arrays and link list </h1>
     <h3>Arrays: </h3> Arrays are allocated in contiguous memory locations, meaning that all elements are stored together in memory. The size of an  array is fixed when it is created. Insertions and deletions can be inefficient in arrays because elements need to be shifted or moved to maintain the contiguous structure. Insertions and deletions at the beginning or middle of an array can take O(n) time on average, where n is the number of elements. Accessing elements in an array is very efficient using index-based access. It takes O(1) time to access an element directly using its index. Access: O(1), Insertions/Deletions at the end: O(1) or O(n) (if reallocation is needed).
     <h3>LinkList: </h3>
      <p>
         Linked lists consist of nodes that are not necessarily stored in contiguous memory locations. Each node contains both data and a          reference (or pointer) to the next node in the list. The size of a linked list can grow dynamically as nodes are added.
         Linked lists are designed for efficient insertions and deletions, especially when they involve adding or removing nodes from the          beginning or middle of the list. These operations generally take O(1) time if you have a reference to the node.
        Accessing elements in a linked list requires traversing from the head node to the desired node, which takes O(n) time on average         in the worst case. Linked lists have higher memory overhead due to the additional memory required for the node pointers.
       Access: O(n), Insertions/Deletions at the beginning/middle: O(1), Insertions/Deletions at the end: O(n) (if traversal is needed).
        </p>
    <br>
    <br>
  </discription>
  </details>
</details>

