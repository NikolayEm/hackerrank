[Insert a node at a specific position in a linked list](https://www.hackerrank.com/challenges/reverse-a-doubly-linked-list/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=linked-lists)

```csharp
static SinglyLinkedListNode insertNodeAtPosition(SinglyLinkedListNode head, int data, int position)
{
	SinglyLinkedListNode node = head;

    var nodeToInsert = new SinglyLinkedListNode(data);

    for (int i = 0; i < position - 1; i++)
    {
        node = node.next;
    }

    SinglyLinkedListNode tail = node.next;
    nodeToInsert.next = tail;

    node.next = nodeToInsert;

    return head;

}
```
