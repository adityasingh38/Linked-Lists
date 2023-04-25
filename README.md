# Linked Lists in C

A linked list is a linear data structure used in computer programming for storing and organizing collections of data. It consists of a series of nodes, where each node contains data and a reference to the next node in the sequence. The nodes are connected sequentially in a chain-like manner, hence the name "linked" list.

Types of Linked Lists include:

- Singly Linked List
- Singly Circular Linked List
- Doubly Linked List
- Doubly Circular Linked List

In a singly linked list, each node contains data and a reference (often called a "pointer") to the next node in the list. The last node in the list has a reference that points to NULL, indicating the end of the list. Singly linked lists allow for efficient insertion and deletion operations at the beginning of the list, but accessing elements in the middle of the list can be slow as it requires traversing the list from the beginning.

In a doubly linked list, each node contains data, as well as references to both the next and previous nodes in the list. This allows for efficient traversal in both directions, but requires additional memory to store the extra reference to the previous node.

A linked list can be represented as follows:

![Representation of a Linked List](https://www.mycplus.com/ezoimgfmt/cdn.mycplus.com/mycplus/wp-content/uploads/2017/09/linked-list.png?ezimgfmt=ng%3Awebp%2Fngcb1%2Frs%3Adevice%2Frscb1-1)

## Implementing a Singly Linked List in C

```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node in the linked list
struct Node {
    int data;
    struct Node* next;
};

// Function to create a new node with the given data
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed. Exiting...\n");
        exit(1);
    }
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a new node at the beginning of the linked list
struct Node* insertAtBeginning(struct Node* head, int data) {
    struct Node* newNode = createNode(data);
    newNode->next = head;
    return newNode;
}

// Function to insert a new node at the end of the linked list
struct Node* insertAtEnd(struct Node* head, int data) {
    struct Node* newNode = createNode(data);
    if (head == NULL) {
        return newNode;
    }
    struct Node* current = head;
    while (current->next != NULL) {
        current = current->next;
    }
    current->next = newNode;
    return head;
}

// Function to display the linked list
void display(struct Node* head) {
    printf("Linked List: ");
    struct Node* current = head;
    while (current != NULL) {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");
}

int main() {
    // Create an empty linked list
    struct Node* head = NULL;

    // Insert nodes at the beginning
    head = insertAtBeginning(head, 3);
    head = insertAtBeginning(head, 2);
    head = insertAtBeginning(head, 1);

    // Insert nodes at the end
    head = insertAtEnd(head, 4);
    head = insertAtEnd(head, 5);

    // Display the linked list
    display(head);

    return 0;
}
```

## Operations supported by Linked Lists in C

1. Insertion at the beginning: Adding a new node with data at the beginning of the linked list. This involves creating a new node, setting its data and next pointer, and updating the next pointer of the new node to point to the previous first node.

2. Insertion at the end: Adding a new node with data at the end of the linked list. This involves creating a new node, setting its data and next pointer, and updating the next pointer of the last node in the linked list to point to the new node.

3. Insertion at a specific position: Adding a new node with data at a specific position in the linked list. This involves creating a new node, setting its data and next pointer, and updating the next pointer of the previous node to point to the new node.

4. Deletion at the beginning: Removing the first node in the linked list. This involves updating the next pointer of the head node to point to the second node and freeing the memory of the removed node.

5. Deletion at the end: Removing the last node in the linked list. This involves updating the next pointer of the second-to-last node to NULL and freeing the memory of the removed node.

6. Deletion at a specific position: Removing a node at a specific position in the linked list. This involves updating the next pointer of the previous node to point to the next node, and freeing the memory of the removed node.

7. Traversal: Accessing and processing each node in the linked list sequentially. This involves starting from the head node, following the next pointers of each node until the end of the list is reached.

8. Searching: Finding the position or presence of a specific value or node in the linked list. This involves traversing the linked list and comparing the data of each node with the target value.

9. Counting: Determining the number of nodes in the linked list. This involves traversing the linked list and incrementing a counter for each node encountered.

10. Reversing: Reversing the order of nodes in the linked list. This involves updating the next pointers of each node to point to the previous node, and updating the head node to point to the last node in the original list.

Linked Lists have a number of advantages over Arrays, some of which are listed below:

- Linked lists have a dynamic size, making them efficient for collections of varying sizes without wasting memory.
- Linked lists allow for efficient insertion and deletion operations, especially at the beginning or end of the list, with a time complexity of O(1).
- Linked lists provide flexibility in memory allocation, as nodes can be allocated individually, making them suitable for situations with fragmented or limited memory.
- Linked lists are relatively simple to implement compared to arrays, as they do not require pre-declaration of size and can be easily modified using basic pointer operations.
- Linked lists are advantageous in scenarios where easy and efficient insertion at the beginning is required, as it can be done in constant time, while inserting at the beginning of an array requires shifting all existing elements.

The program in this repository demonstrates the implementation of Linked Lists in C.

### Code:

```
// Implementing Linked Lists using structures

// printf statement once, stop looping when the pointer finds address NULL

#include <stdio.h>
#include <stdlib.h>

void disp();

struct node
{
	int data;
	struct node *next;
};

struct node *start;

int main()
{
	struct node *newnode1, *newnode2, *newnode3, *newnode4;
	
	newnode1 = (struct node*) malloc(sizeof(struct node));
	newnode2 = (struct node*) malloc(sizeof(struct node));
	newnode3 = (struct node*) malloc(sizeof(struct node));
	newnode4 = (struct node*) malloc(sizeof(struct node));
	
	newnode1 -> data = 10;
	newnode1 -> next = newnode2;
	
	start = newnode1;
	
	newnode2 -> data = 20;
	newnode2 -> next = newnode3;
	
	newnode3 -> data = 30;
	newnode3 -> next = newnode4;
	 
	newnode4 -> data = 40;
	newnode4 -> next = NULL;
	
	disp();
	
	return 0;
	
	
	/*
	struct node *newnode1, *newnode2, *newnode3, *newnode4;
	
	newnode1 = (struct node*) malloc(sizeof(struct node));
	newnode2 = (struct node*) malloc(sizeof(struct node));
	newnode3 = (struct node*) malloc(sizeof(struct node));
	newnode4 = (struct node*) malloc(sizeof(struct node));
	
	newnode1 -> data = 10;
	newnode1 -> next = newnode2;
	
	newnode2 -> data = 20;
	newnode2 -> next = newnode3;
	
	newnode3 -> data = 30;
	newnode3 -> next = newnode4;
	 
	newnode4 -> data = 40;
	newnode4 -> next = NULL;
	
	printf("data 1: %d	selfaddr 1: %d	nextaddr 1: %d\n", newnode1 -> data, newnode1, newnode1 -> next);
	printf("data 2: %d	selfaddr 2: %d	nextaddr 2: %d\n", newnode2 -> data, newnode2, newnode2 -> next);
	printf("data 3: %d	selfaddr 3: %d	nextaddr 3: %d\n", newnode3 -> data, newnode3, newnode3 -> next);
	printf("data 4: %d	selfaddr 4: %d	nextaddr 4: %d\n", newnode4 -> data, newnode4, newnode4 -> next);
	*/
	
}


// function to display the linked list elements
void disp()
{
	struct node *temp;
	
	temp = start;
	
	while(temp != NULL)
	{
		printf("data: %d	selfaddr: %d	nextaddr: %d\n", temp -> data, temp, temp -> next);
		temp = temp -> next;
	}
}
```

### Output:

![linkedLists.c output](https://github.com/Aditi-exe/C-Linked-Lists/blob/main/linkedLists1.PNG)
