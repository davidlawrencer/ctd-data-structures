```ruby

# Stack using array as underlying data collector 
# we'll manipulate the element at the last index, since it supports O(1) operations

class ArrayStack
  def initialize
    @list = []
  end

  def push(value)
    @list.append(Node.new(value))
  end
  
  def pop
    @list.pop()
  end

  def top
    @list.last
  end

  def isEmpty
    @list.empty?
  end
end

# Stack using LinkedList as underlying data collector 
# we'll manipulate HEAD, since it supports O(1) operations

class LLStack
  def initialize
    @list = LinkedList.new()
  end

  def push(value)
    node = Node.new(value)
    node.next = @list.head
    @list.head = node
  end
  
  def pop
    newHead = @list.head.next
    value = @list.head.value
    @list.head = newHead
    value
  end
  
  def top
    value = @list.head.value
    value
  end
  
  def is_empty?
    @list.head.nil?
  end
end

```
