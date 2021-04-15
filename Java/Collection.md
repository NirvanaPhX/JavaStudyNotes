## **Collection**
- Collection is the top interface used to store and retrieve single value data 
- It implements the Iterable interface. 
- Common method used in Collection:
  1. boolean add(E e)
  2. boolean remove(Object o)
  3. void clear()
  4. boolean contains(Object o)
  5. boolean isEmpty()
  6. int size()
- Iterator<E> iterator() is the method that returns an Itr() object to iterate through a collection.
- Iterator is dependent on Collection.
- Common method of Iteratr:
  1. E next() (may throw NoSuchElementException if request an element outside of the collection.
  2. boolean hasNext()

### List
- List is an interface for an **ordered** collection, it has an index and provides additional methods for positional(indexed) access.
- It extends the Collection<E> interface.
- Different from Set, List **allows duplicate** element.
- Additional Method:
  1. void add(int index, E element)
  2. E remove(int index)
  3. E set(int index, E element)
  4. E get(int index)
- ConcurrentModificationException: This is caused by Modification counts changed when using iterator. 
    ```java
    List<String> list = new ArrayList<String>();
    
    list.add("Monday");
    list.add("Tuesday");
    list.add("Wednesday");
    
    Iterator<String> it = list.iterator();
    while(it.hasNext()) {
      String s = it.next();
      if (s.equals("Wednesday")) {
        list.add("Thursday");
      }
    }
    ```
    *** This code snippet throws ConcurrentModificationException.
    
    The implementations of the iterator() and add() method are as follow:
    ```java
    public boolean add(E e) {
      modCount++;
      add(e, elementData, size);
      return true;
    }
    
    public Iterator<E> iterator() {
      // Assign actual modification counts to expected modification counts
      int expectedModCount = modCount; 
      
      public E next() {
        checkFormComodification();
        int i = cursor;
        if (i >= size)
          throw new NoSuchElementException();
        Object[] elementData = ArrayList.this.elementData;
        if (i >= elementData.length)
          throw new ConcurrentModificationException();
        curosr = i + 1;
        return (E) elementData[lastRet = i];
        
      final void checkForComodification() {
        if (modCount != expectedModCount) 
          throw new ConcurrentModificationException();
          }
      }
    ```
    *** The problem can be fixed using for loop to iterator through the List.
  ```
  for (int i=0; i<list.size(); i++) {
    String s = list.get(i);
    if(s.equals("Wednesday")) {
      list.add("Thursday");
    }
  }
  ```
  - __ListIterator__ is an interface extends Iterator<E>. 
      - It allows __bidirection__ traverse, modify the list during iteration and obtain the iterator's current position.
      - ListIterator lies between elements. If you want to return an element, you have to call next() or previous() to move the cursor 
        and it will return the element went through by the cursor. 
      - Common methods:
        1. E next();
        2. boolean hasNext()
        3. E previous()
        4. boolean hasPrevious()
        5. void add(E e) // Won't raise the ConcurrentModificationException.
        ```java
        private class ListItr extends Itr implements ListIterator<E> {
          public void add(E e) {
            checkForComodification(); // Still checks the expected and actual value of modification counts
            
            try {
              int i = cursor;
              ArrayList.this.add(i, e);
              cursor = i + 1;
              lastRet = -1;
              expectedModCount = modCount; // After modification, reassign actual value to expected modification counts
            } catch (IndexOutOfBoundsException ex) {
              throw new CouncurrentModificationException();
            }
          }
        }
        ```
    

## Map
- Map is the other interface similar to Collection but stores data in a key/value pair.
