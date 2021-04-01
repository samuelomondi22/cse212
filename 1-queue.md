
**Queue**

1. **MC Story Queue**
Queue follows the principle of First In First Out (FIFO). This is when the first data to be entered is the first to be taken out. 
Imagine going to buy tickets for an event in the MC building. On your arrival you find a long line and have to be at the back. The way this works is that the first person to come buy the ticket is the first person to get a ticket and leave while you have to stay in line waiting your turn. 

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
This uses the insert() method to insert items at the front.

<code>def enqueue(self, data): 
    self.items.insert(0, data) 
    self.size += 1 </code>

The first position of a list is index 0 hence as you see the insertion indicate 0 on the method. The insert operation will shift existing data elements in the list by one position up and then insert the new data in the space created at index 0. self.size += 1 reflects the addition of a new element. 

<img src="/node.jpg">

3. **Dequeue Operation**
It ois used to remove items from the queue. 

<code>def dequeue(self):
    self.items.pop()
    self.size -= 1
    return data</code>

The pop() is a method that removes last item from the list. self.size -= 1 reflects the removal of am element.

<img src="/dequeue.jpg">

**Example:**

**Problem**

