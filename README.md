 # My-learning-journey.
## topics
<details>
  <summary>data struture</summary>
  <h1>What is data struture</h1>
  <P>Data structure is a specialized format for organizing, sorting, and manipulating data. It defines the relationship between data and operations that can be performed on data.  Properly designed data structures can provide efficient methods for data retrieval, insertion, deletion, and sorting.</P>

  <details>
    <summary>Topic: 1</summary>
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
   <summary>LinkLIst Code in C++</summary>
   <discription>
    <h2>Code of linked list </h2>
    <h3>How to create a linked list in C++ and how to append an element at its beginning.</h3>
    <p>
     
     #include <iostream>
     using namespace std; 

     class Node { 
     public: 
       int data;   // For integer data 
       Node *next; // to point next data address 
   
    Node(int data) { 
      this->data = data; 
      next = nullptr; 
    } 
    }; 
     
    // class LinkList represents the link itself and we define methods to append and 
    // display the elements of the link list 
    class LinkList { 
    public: 
      Node *head; 
      LinkList() { head = nullptr; } 
      // Now we define the method to add a new element in the link list 
      void append(int data) {
        Node *newNode = new Node(data);
        if (head == nullptr) { 
          head = newNode;
        } else {
          Node *current = head; // store head pointer value 
          while ( current->next != nullptr) { // this condition works until the next pointer is Nullptr
            current = current->next;
          }
          current->next = newNode;
        }<br>
      }
    
      void display() { 
        Node *current = head; // store head pointer value 
        while (current != nullptr) { //This condition works until the next pointer is Nullptr 
          cout << current->data << " ";
          current = current->next;
        }
        cout << endl;
      }<br>
      // Method to check if the linked list is empty
      bool isEmpty() { return head == nullptr; 
      }
    };
    
    int main() {
      LinkList myList; // create an object. it creates a link list of myList<br>
      myList.append(5);
      myList.append(7);
      myList.append(12);
      myList.display(); 
      return 0; <br>
    }


    
   </discription>
  </details>
  <details>
   <summary>array Fundamental Code</summary>
   <details>
    <summary>Insertion</summary>
    
`      #include <iostream>
       using namespace std;
 
       int main() {
         const int MAX_SIZE = 5; // array maz size
         int arr[MAX_SIZE] = {1, 2, 3, 5};
         int size = sizeof(arr)/sizeof(arr[0]); // current size of array
         int newIndex = 3;
         int newValue = 4;
       
         for(int i = size; i > newIndex; i--){
           arr[i] = arr[i - 1];
         }
       
         arr[newIndex] = newValue;
         
         cout << "Array after Insertion: "<< endl;
         for(int i = 0; i < size; i++){
           cout << arr[i] << " ";
         }
       
       
         return 0;
       }
`
   </details>
<details>
    <summary>Deletion</summary>
 
 `         #include <iostream>
           using namespace std;
           
          int main() {
            const int MAX_SIZE = 5; // array maz size
            int arr[MAX_SIZE] = {1, 2, 3, 4, 5};
            int size = sizeof(arr)/sizeof(arr[0]); // current size of array
          
            int deleteIndex = 3;
          
            for(int i = deleteIndex; i < size -1; i++){
              arr[i] = arr[i + 1];
            }
          
            size--;
            cout << "Array after Insertion: "<< endl;
            for(int i = 0; i < size; i++){
              cout << arr[i] << " ";
            }
          
          
            return 0;
          }
   </details>
<details>
  <summary>find the index of highest number</summary>
         #include "iostream"
        using namespace std;
             
     int main(){
       int arr[]= {1,3,4,7};
       int size = sizeof(arr)/sizeof(arr[0]);
       int Index = 0;
       int max_num = 0;
     
       for(int i =0; i < size; i++){
         if(arr[i] > max_num){
           max_num = arr[i];
           Index = i;
         }
       }
       cout<<"Max Number: " << max_num << endl;
       cout << "index of max numebr: " <<Index << endl;
       return 0;
     }

 </details>
   
   
  </details>
</details>

