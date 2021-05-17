# WORK IN PROGRESS

```ruby

class ArrayQueue

  def initialize
    @list = []
  end
  
  def enqueue(value) 
  end

  def dequeue
  end

  def front
  end 
  
  def isEmpty
  end
end

class LLQueue 

  def initialize
  end
  
  def enqueue(value) 
  end

  def dequeue
  end

  def front
  end 
  
  def isEmpty
  end
end

# Helper classes

class Node
  attr_accessor :next
  attr_reader   :value
  def initialize(value)
    @value = value
    @next  = nil
  end
end

class LinkedList
  def initialize
    @head = nil
    @tail = nil
  end
end

```
