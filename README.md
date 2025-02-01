package stacklist;

// This file contains the Stack and Node classes


class Node {
    int data;
    Node next;

    Node(int new_data) {
        this.data = new_data;
        this.next = null;
    }
}

public class Stack {
    private Node head;

    public Stack() {
        this.head = null;
    }

    public boolean isEmpty() {
        return head == null;
    }
     public void push(int new_data) {
        Node new_node = new Node(new_data);
        new_node.next = head; // Link the new node to the current top
        head = new_node; // Update the top to the new node
    }

    public void pop() {
        if (isEmpty()) {
            System.out.println("\nStack Underflow");
            return;
        }
        head = head.next; // Update the top to the next node
    }

    public int peek() {
        if (!isEmpty())
            return head.data;
        else {
            System.out.println("\nStack is empty");
            return Integer.MIN_VALUE; // Intentional mistake: should be MAX_VALUE for testing error
        }
    }
}




