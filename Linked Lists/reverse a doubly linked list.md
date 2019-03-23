[Reverse a doubly linked list](https://www.hackerrank.com/challenges/reverse-a-doubly-linked-list/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=linked-lists)

## My notes
As a solution, I'm using new linked list object with reversed data from the source

```csharp
static DoublyLinkedListNode reverse(DoublyLinkedListNode head)
{
    if (head == null)
    {
        return null;
    }

    var buffer = new List<int>
    {
        head.data
    };

    DoublyLinkedListNode node = head.next;

    // while have nodes, extend buffer
    while (node != null)
    {
        buffer.Add(node.data);

        node = node.next;
    }

    var result = new DoublyLinkedList();

    // LINQ reverse
    buffer.Reverse();

    // loop thru reversed buffer and create output which is equal to original but reversed
    foreach(int data in buffer)
    {
        result.InsertNode(data);
    }

    return result.head;
}
```

### 2nd solution - do not create new list, update referenced
```csharp
static DoublyLinkedListNode reverse(DoublyLinkedListNode head)
    {
        if (head == null)
        {
            return null;
        }

        DoublyLinkedListNode last = null;
        DoublyLinkedListNode node = head;

        while (node != null)
        {
            last = node.prev;
            node.prev = node.next;
            node.next = last;
            node = node.prev;
        }

        return last != null ? head = last.prev : head;
    }
```