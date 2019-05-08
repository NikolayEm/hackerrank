[Sherlock and the Valid String](https://www.hackerrank.com/challenges/sherlock-and-valid-string/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=strings)


```csharp
static string isValid(string s)
{
    bool isValid = false;

    int[] table = new int[26];
    s.ToList().ForEach(_ => table[_ - 'a']++);

    int[] map = table.Where(_ => _ != 0).ToArray();

    if (map.Distinct().Count() == 1)
    {
        isValid = true;
    }
    else if (map.Distinct().Count() <= 2)
    {
        IEnumerable<int> groups = map.GroupBy(_ => _).Select(_ => _.Count());
        int cnt = groups.TakeWhile(_ => _ > 1).Count();

        isValid = cnt == 1;
    }

    return isValid ? "YES" : "NO";
}
```
