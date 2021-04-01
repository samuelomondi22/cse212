
**Linked List**

This is a type of list where data can be stored in any location. There is no guarantee that one element will be next to each other. The elements are called nodes and they have a pointer to show the location in memory.

<img src="/linkedlist.webp">

While inserting you do not have to move every element over. The first part of the list is called a node while the last not is called a tail.

- ***inserting at the beginning***

Inserting at the beginning means you have to put the pointer to the current head of the linked list and then making it become the second data element while the new node becomes the head. Inserting or removing at the beginning requires a performance of O(1)

<img src="/Linkedlist_insert_at_start.png">

It is a 4 step process that requires:
    - creating a new node
    - setting up the new node to be next
    - setting previous node of current head to be the new node
    - finally making the head to equal the new node

- ***inserting at the end***
This involves pointing the next pointer of the the current last node of the linked list to the new data node. Inserting or removing at the tail requires an O(1) performance.

<img src="/Linkedlist_insert_last.png">

It involves the following steps:
    - creating a new node
    - setting up the previous new node to be the tail
    - setting up the next of current tail be the new node
    - finally making the tail to equal the new node

- ***inserting in the middle***
This involves a 5 step process:

<img src="/Linkedlist_insert_middle.png">
    - creating a new node
    - setting up the previous node to be the current node
    - setting up next of new node to the next node after the current node
    - setting up the previous of the next node after the current new node
    - finally making the current node to equal the new node

Inserting or removing at the middle requires a performance of O(n) and this is because a loop is required. 

**Example**

**Problem**
