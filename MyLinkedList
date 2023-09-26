import java.util.NoSuchElementException;

public class MyLinkedList implements MyList {
    // Implement the required fields and methods here
    private Node head = null;
    private int size = 0;
    private Node tail = null;
   
   public void print(Node dog){
      System.out.print(dog.data);
      
   }
   
   public void printAll(){
      Node printer = new Node();
      printer = head;
      
      while (printer != null){
         print(printer);
         if (printer.next != null){
         printer = printer.next;
         } else {printer = null;}
      }
   }
   
   
    public void addToEnd(Object newN){
      Node yes = new Node();
      yes.data = newN;
       if (head == null){
          head = yes;
          head.next = null;
          tail = head;
       } else{
          tail.next = yes;
          tail = yes;
          } 
       size++;
    }
    
    public void insertAt(int index, Object newN){
      int location = 0;
      
      Node newNode = new Node();
      newNode.data = newN;
      
      if (index == 0){
         newNode.next = head;
         head = newNode;
      } else if ((index < 0) || (index > size)){
        throw new NoSuchElementException();
      } else if (index == size){
         tail.next = newNode;
         tail = newNode;
         newNode.next = null;
      } else { 
         Node myit = head;
         while (location != (index-1)){
            myit = myit.next;
            location++;  
         }
         Node newNext = myit.next;
         myit.next = newNode;
         newNode.next = newNext;
      }
      size++;
    }
    
    public Object getAt(int index){
    int location = 0;
     if ((index < 0) || (index >= size)){
        throw new NoSuchElementException();
      } else { 
      Node myit = head;
         while (location != (index)){
            myit = myit.next;
            location++;  
         }
         return myit.data;
      }
    }
    
    public void removeAt(int index){
       int location = 0;
     if ((index < 0) || (index >= size)){
        throw new NoSuchElementException();
      } else if (index == 0){
         head = head.next;
      } else  { 
      Node myit = head;
         while (location != (index-1)){
            myit = myit.next;
            location++;  
         }
         Node newNext = myit.next;
       myit.next = newNext.next;
    }
    size--;
    }
    
    
    public int getSize(){
      return size; 
    }
    
   
	// Do not alter the code below 
	
	public MyListIterator getIterator() {
		return new MyLinkedListIterator();
	}
	
	private class MyLinkedListIterator implements MyListIterator {
		Node currentNode = null;

		@Override
		public Object next() {
			if (currentNode != null)
				currentNode = currentNode.next;
			else
				currentNode = head;

			return currentNode.data;
		}

		@Override
		public boolean hasNext() {
			if (currentNode != null)
				return currentNode.next != null;
			else
				return head != null;
		}
	}
	
	class Node {
		public Object data = null;
		public Node next = null;
	}
}