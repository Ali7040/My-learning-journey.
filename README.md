 # My-learning-journey.
## topics
<details>
  <summary>data structure and Algo</summary>
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
    <summary>Topic: 2 (What is the stack?)</summary>
  <discription> 
    <h1> Stack </h1>
        <h3>Stack: </h3> 
            a stack is a data structure that follows the Last In First Out (LIFO) principle. Think of it as a stack of plates where you can only add or remove plates from the top.
        <h3>Basic Operations:</h3>
            Push: Adding an item to the stack is called pushing. The item is added to the top of the stack. <br>
            Pop: Removing an item from the stack is called popping. The top item is removed from the stack.<br>
            Peek or Top: Viewing the top item without removing it from the stack.<br>
            IsEmpty: Checking if the stack is empty.<br>
            IsFull: Checking if the stack is full (in cases where the stack has a fixed size).<br>

  </discription>
  </details>
  
  <details> 
   <summary>LinkLIst Code in C++ with all basic Operations</summary>
   <discription>
    <h2>Code of linked list </h2>
    <h3>How to create a linked list in C++ and append an element at its beginning. Insert At the end and also Insert at mid of the LinkedList and how can we traverse the linkedlist</h3>
    <p>
    
     
     
     
     class Node {
     public:
       int data;
       Node *Next;
     
       Node(int val){
         data = val;
         Next = nullptr;
       }
     };
     
     class LinkedList{
       Node *head;
       Node *tail;
       int size;
     public:
       LinkedList(){
         head = nullptr;
         tail = nullptr;
         size = 0;
       }
      void Insert(int val){
        Node *newNode = new Node(val);
        if(head == nullptr){
          head = newNode;
          tail = newNode;
          size++;
        }
        else{
          tail->Next = newNode;
          tail = newNode;
          size++;
          tail->Next = head;
        }
      }
     void InsertAtMiddle(int val) {
         Node *newNode = new Node(val);
     
         if (size == 0) {
             head = newNode;
             tail = newNode;
             newNode->Next = head;
             size++;
         } else {
             Node *temp = head;
             int mid = size / 2;
             while (mid > 1) {
                 temp = temp->Next;
                 mid--;
             }
     
             newNode->Next = temp->Next;
             temp->Next = newNode;
             size++;
         }
     }
     
     void DeleteAtFirst(){
       if(size == 0){
         cout << "List is empty. Cannot delete from an empty list." << endl;
         return;
       }
       else if( size == 1){
         delete head;
         head = nullptr;
         tail = nullptr;
         size--;
       }
       else{
         Node * temp = head;
         head = head->Next;
         tail->Next = head;
         delete temp;
         size--;
       }
     }
     
     
     
     
     
     
     
     void Print() {
         Node *current = head;
         do {
             cout << current->data << " ";
             current = current->Next;
         } while (current != head);
     
         cout << endl;
     }
     
     
     };
     
     
     int main(){
       LinkedList myList;
       myList.Insert(10);
       myList.Insert(20);
       myList.Insert(40);
       myList.Insert(50);
       myList.InsertAtMiddle(15);
       myList.Print();
       myList.Insert(100);
       myList.Print();
       myList.DeleteAtFirst();
       myList.Print();
       return 0;
     }


    
   </discription>
  </details>

  <details> 
   <summary>Reverse the LinkLIst Code in C++</summary>
   <discription>
    <h2>Code of linked list </h2>
    <h3>How to reverse the linkedlist in C++</h3>
    <p>
            
     ListNode* reverseList(ListNode* head) {
               if (head == nullptr || head->next == nullptr) {
               return head;
           }
           
           ListNode* restReversed = reverseList(head->next);
           head->next->next = head;
           head->next = nullptr;
           
           return restReversed;
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


    
    `          #include <iostream>
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
 <details>
  <summary>Traverse the 2D-Array</summary>
  
      int main(){
       const int Row = 3;
       const int Col = 3;
      int arr[Row][Col] = {
          {1,2,3},
          {4,5,6},
          {7,8,9}
        };
       int size = sizeof(arr)/ sizeof(arr[0][0]);
      
        for(int i = 0 ; i < Row; i++){
          for(int j = 0; j < Col; j++){
            cout << arr[i][j] <<endl;
          }
        }
      
        return 0;
      }

 </details>
   
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
 <details>
  <summary>Algo Empirical Analysis</summary>

  
               #include <iostream>
                
               #include <chrono>
               using namespace std;
         
         int main() {
             auto start = chrono::high_resolution_clock::now();
         
             // Code to be analyzed
         
             auto stop = chrono::high_resolution_clock::now();
             auto duration = chrono::duration_cast<chrono::microseconds>(stop - start);
         
             cout << "Time taken: " << duration.count() << " microseconds" << endl;
         
             return 0;
         }

 </details>
 
   <details>
  <summary>Stack using array</summary>
     #include <iostream>
   using namespace std;
   
   const int MAX_SIZE = 100; // Maximum size of the stack

class Stack {
private:
    int top; // Index of the top element in the stack
    int arr[MAX_SIZE]; // Array to store stack elements

public:
    // Constructor to initialize the stack
    Stack() {
        top = -1; // Stack is initially empty
    }

    // Function to push an element onto the stack
    void push(int value) {
        if (top >= MAX_SIZE - 1) {
            cout << "Stack overflow! Cannot push element " << value << endl;
        } else {
            arr[++top] = value;
            cout << "Pushed " << value << " onto the stack." << endl;
        }
    }

    // Function to pop an element from the stack
    void pop() {
        if (top < 0) {
            cout << "Stack underflow! Cannot pop from an empty stack." << endl;
        } else {
            cout << "Popped " << arr[top--] << " from the stack." << endl;
        }
    }

    // Function to check if the stack is empty
    bool isEmpty() {
        return top < 0;
    }

    // Function to peek at the top element of the stack
    int peek() {
        if (top < 0) {
            cout << "Stack is empty." << endl;
            return -1; // Return a sentinel value indicating an empty stack
        }
        return arr[top];
        }
       };
      
    int main() {
       Stack stack;
       stack.push(1);
       stack.push(2);
       stack.push(3);
   
       cout << "Top element: " << stack.peek() << endl;
   
       stack.pop();
       cout << "Top element after pop: " << stack.peek() << endl;
   
       stack.pop();
       stack.pop();
       stack.pop(); // Trying to pop from an empty stack
   
       return 0;
        }

           
 </details> 
 </details>
   
  </details>

</details>

