```ruby

# Node class: holds our data, and has a reference to the next node. That's it!


class Node
  attr_accessor :next
  attr_reader   :value
  def initialize(value)
    @value = value
    @next  = nil
  end
  def to_s
    "Node with value: #{@value}"
  end
end

# Linked List class: knows where the HEAD node is, and uses that position to add, remove, and look through values in the chain of nodes.
# When a user interfaces with the Linked List class, they should not have to know about Nodes. They are looking for the values that these nodes contain!

class LinkedList
  def initialize
    @head = nil
  end
  
# some sample LL functions. You could make tons of them!
  
  def addToFront(value)
    node = Node.new(value)
    if @head
      node.next = @head
    end
    @head = node
  end
  
  def printAllValues
    node = @head
    puts node
    while (node = node.next)
      puts node
    end
  end
  
  def isEmpty
    return @head.nil?
  end
  
end

```
