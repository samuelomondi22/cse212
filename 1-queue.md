
**Queue**

1. **MC Story Queue**
<p>Queue follows the principle of First In First Out (FIFO). This is when the first data to be entered is the first to be taken out. 
Imagine going to buy tickets for an event in the MC building. On your arrival you find a long line and have to be at the back. The way this works is that the first person to come buy the ticket is the first person to get a ticket and leave while you have to stay in line waiting your turn. </p>

<img src="/queue-at-a-bank.png">

Most data structures are built on queues. Making it the most fundamental and important concept. 

To join the queue(enqueue), you must move behind the last person in the queue. Once one is served he has the opportunity to leave the queue(dequeue). 

| ***Queue*** | ***Size*** | ***Contents*** | ***Performance*** |
| ----------- | ---------- | -------------- | ----------------- |
| Queue() | 0 | [] | O(1) |
| Enqueue "Mark" | 1 | ['mark'] | 0(1) |
| Enqueue "John" | 2 | ['mark', 'john'] | O(1) |
| Size() | 2 | ['mark', 'john'] | O(1) |
| Dequeue() | 1 | ['mark'] | O(n) in a dynamic array everything is shifted to fill the empty place while for a linked list the performance is O(1)|


2. **Enqueue Operation**
<p>This uses the insert() method to insert items at the front.</p>

```
def enqueue(self, data): 
    self.items.insert(0, data) 
    self.size += 1 
```

The first position of a list is index 0 hence as you see the insertion indicate 0 on the method. The insert operation will shift existing data elements in the list by one position up and then insert the new data in the space created at index 0. self.size += 1 reflects the addition of a new element. 

<img src="/node.jpg">

3. **Dequeue Operation**
<p>It is used to remove items from the queue.</p>

```
def dequeue(self):
    self.items.pop()
    self.size -= 1
    return data
```

The pop() is a method that removes last item from the list. self.size -= 1 reflects the removal of am element.

<img src="/dequeue.jpg">

**Example: Simple Queue**
Here we will simply see how to basically enqueue and dequeue code.

```
class Queue:
    def __init__(self, capacity):
        self.front = self.size = 0
        self.rear = capacity - 1
        self.Q = [None] * capacity
        self.capacity = capacity

    def isFull(self):
        return self.size == self.capacity

    def isEmpty(self):
        return self.size == 0

    def EnQueue(self, item):
        if self.isFull():
            print("Full")
            return

        self.rear = (self.rear + 1) % (self.capacity)
        self.Q[self.rear] = item
        self.size = self.size + 1
        print("%s enqueue to queue" %str(item))

    def DeQueue(self):
        if self.isEmpty():
            return "Empty"

        print("%s dequeued from queue" %str(self.Q[self.front]))
        self.front = (self.front + 1) % (self.capacity)
        self.size = self.size - 1

    def que_front(self):
        if self.isEmpty():
            print("The Queue is empty")


        print("Front item is ", self.Q[self.front])

    def que_rear(self):
        if self.isEmpty():
            print("Queue is Empty")

        print("The rear item is ", self.Q[self.rear])


queue = Queue(30)
queue.EnQueue(10)
queue.EnQueue(20)
queue.EnQueue(30)
queue.EnQueue(40)
queue.EnQueue(50)
queue.que_front()
print()
queue.DeQueue()
queue.que_front()
queue.que_rear()
print()
queue.DeQueue()
queue.que_front()
queue.que_rear()
```

**Problem**
Write a Python program to create a queue and display all the members and size of the queue. 

When done, take a look at the [solution](/1-queue.py)
