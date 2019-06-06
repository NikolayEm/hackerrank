[Pangrams](https://www.hackerrank.com/challenges/pangrams/problem)

## Implementation via LINQ

```csharp
static int minimumAbsoluteDifference(int[] arr)
{
  string normalized = s.ToLower();
  char[] unique = normalized.Distinct().Where(c => c != ' ').ToArray();

  return unique.Length == 26 ? "pangram" : "not pangram";
}
```

## Implementation without LINQ

```csharp
static string pangrams(string s)
{
    string normalized = s.ToLower();

    var hashMap = new HashSet<char>();

    for (int i = 0; i < normalized.Length; i++)
    {
        char current = normalized[i];

        if (current != ' ' && !hashMap.Contains(current))
        {
            hashMap.Add(current);

            if (hashMap.Count == 26)
            {
                return "pangram";
            }
        }
    }

    return "not pangram";
}
```
