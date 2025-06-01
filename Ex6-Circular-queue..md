# Ex6 Dequeue Elements from Circular Queue
## DATE:
## AIM:
To write a C program to delete three elements from the filled circular queue.

## Algorithm
1. Check if queue is empty
   If empty, display error and return -1
   If not empty, proceed to remove element at front position
2. Store front element for return
   Save the value at current front index before removal
3. Update front position
   If only one element exists, reset front and rear to -1
   For multiple elements, move front circularly using modulo operation
4.  Return the removed element
    Output the stored element value to caller
5.  Repeat for multiple deletions
    For deleting three elements:
    a) Perform steps 1-4 three times
    b) After each deletion, print which element was removed
    c) If queue empties early, stop and notify 

## Program:
```
Program to delete three elements from the filled circular queue
Developed by: S Mohamed Ahsan
RegisterNumber:  212223240089

int deQueue() {
  int element;
  if (isEmpty()) {
    printf("Queue is empty !!\n");
    return (-1);
  } else {
    element = items[front];
    if (front == rear) {
      front = -1;
      rear = -1;
    } else {
      front = (front + 1) % SIZE;
    }
    return (element);
  }
}

void deleteThreeElements() {
  for (int i = 0; i < 3; i++) {
    int removed = deQueue();
    if (removed != -1) {
      printf("Deleted element %d -> %d\n", i+1, removed);
    } else {
      printf("Queue became empty after %d deletions\n", i);
      break;
    }
  }
}
```

## Output:
![Screenshot 2025-04-29 205043](https://github.com/user-attachments/assets/267b1c58-2e8e-4a6a-969c-8fbd74c6d942)


## Result:
Thus, the C program to delete three elements from the filled circular queue is implemented successfully.
