[Two Strings](https://www.hackerrank.com/challenges/two-strings/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=dictionaries-hashmaps)

```csharp
static string twoStrings(string s1, string s2)
{
    var map = new HashSet<char>(s1.ToArray());

    foreach(char a in s2)
    {
        if (map.Contains(a))
        {
            return "YES";
        }
    }

    return "NO";
}
```
