[Pangrams](https://www.hackerrank.com/challenges/pangrams/problem)

```csharp
static int minimumAbsoluteDifference(int[] arr)
{
  string normalized = s.ToLower();
  char[] unique = normalized.Distinct().Where(c => c != ' ').ToArray();

  return unique.Length == 26 ? "pangram" : "not pangram";
}
```
