[Inserting a Node Into a Sorted Doubly Linked List](https://www.hackerrank.com/challenges/insert-a-node-into-a-sorted-doubly-linked-list/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=linked-lists)

```csharp
static DoublyLinkedListNode sortedInsert(DoublyLinkedListNode head, int data)
{
    var insert = new DoublyLinkedListNode(data);

    if (head.data > data)
    {
        insert.next = head;
        head.prev = insert;
        head = insert;
    }
    else
    {
        DoublyLinkedListNode current = head;

        while (current.next != null && current.next.data < data)
        {
            current = current.next;
        }

        insert.prev = current;
        insert.next = current.next;
        current.next = insert;
    }

    return head;
}
```
