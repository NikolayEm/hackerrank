[HackerRank in a String!](https://www.hackerrank.com/challenges/hackerrank-in-a-string/problem)

## Implementation with queue usage

```csharp
static string hackerrankInString(string s)
{
    const string instance = "hackerrank";

    var queue = new Queue<char>();

    foreach(char c in instance)
    {
        queue.Enqueue(c);
    }

    foreach(char current in s)
    {
        char q = queue.Peek();

        if (current == q)
        {
            queue.Dequeue();

            if (!queue.Any())
            {
                return "YES";
            }
        }
    }

    return "NO";
}
```

## Simplified implementation

```csharp
static string hackerrankInString(string s)
{
    const string instance = "hackerrank";

    int len = 0;

    for (int i = 0; i < s.Length; i++)
    {
        if (s[i] == instance[len])
        {
            len++;

            if (len == instance.Length)
            {
                return "YES";
            }
        }
    }

    return "NO";
}
```
