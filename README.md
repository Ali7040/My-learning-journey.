 # My-learning-journey.
## topics
<details>
  <summary>data struture</summary>
  <h1>What is data struture</h1>
  <P>Data structure is a specialized format for organizing, sorting, and manipulating data. It defines the relationship between data and operation that can be performed on data.  Properly designed data structures can provide efficient methods for data retrieval, insertion, deletion, and sorting.</P>

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
  <details> 
   <summary>day 2</summary>
   <discription>
    <h2>Code of linked list </h2>
    <h3>How to create a linked list in C++ and how to append an element at its beginning.</h3>
    <p>
     
     #include <iostream> <br>
     using namespace std; <br>

class Node { <br>
public: <br>
  int data;   // For integer data <br>
  Node *next; // to point next data address <br>

  Node(int data) { <br>
    this->data = data; <br>
    next = nullptr; <br>
  } <br>
}; <br>
 <br>
// class LinkList represent the link itself and we define methods to append and <br>
// display the elemnts of linklist <br>
class LinkList { <br>
public: <br>
  Node *head; <br>
  LinkList() { head = nullptr; } <br>
  // Now we define the method to add new element in linkList <br>
  void append(int data) { <br>
    Node *newNode = new Node(data); <br> 
    if (head == nullptr) { <br>
      head = newNode;<br>
    } else {<br>
      Node *current = head; // store head pointer value <br>
      while ( current->next != nullptr) { // this condition works until the next pointer is Nullptr<br>
        current = current->next;<br>
      }<br>
      current->next = newNode;<br>
    }<br>
  }<br>

  void display() { <br>
    Node *current = head; // store head pointer value <br>
    while (current != nullptr) { //This condition works until the next pointer is Nullptr <br>
      cout << current->data << " ";<br>
      current = current->next;<br>
    }<br>
    cout << endl;<br>
  }<br>
  // Method to check if the linked list is empty<br>
  bool isEmpty() { return head == nullptr;<br> }<br>
};<br>

int main() {<br>
  LinkList myList; // create an object. it creates a link list of myList<br>
  myList.append(5);<br>
  myList.append(7);<br>
  myList.append(12);<br>
  myList.display(); <br>
  return 0; <br>
}
<br>
<br>
    </p>
   </discription>
  </details>
</details>

