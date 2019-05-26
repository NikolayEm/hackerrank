[Making Anagrams](https://www.hackerrank.com/challenges/ctci-making-anagrams/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=strings)


```csharp
static int makeAnagram(string a, string b)
{
    int deleted = 0;

    if (a == b)
    {
        return 0;
    }

    Dictionary<char, int> a1 = a.OrderBy(_ => _).GroupBy(_ => _).ToDictionary(_ => _.Key, _ => _.Count());
    Dictionary<char, int> b1 = b.OrderBy(_ => _).GroupBy(_ => _).ToDictionary(_ => _.Key, _ => _.Count());

    foreach (KeyValuePair<char, int> item in a1)
    {
        if (!b1.ContainsKey(item.Key))
        {
            deleted += item.Value;
        }
        else
        {
            deleted += Math.Abs(item.Value - b1[item.Key]);
        }
    }

    foreach (KeyValuePair<char, int> item in b1)
    {
        if (!a1.ContainsKey(item.Key))
        {
            deleted += item.Value;
        }
    }

    return deleted;
}
```

### 2nd solution - play char as int
```csharp
static int makeAnagram(string a, string b)
{
    var table = new int[26];

    a.ToList().ForEach(_ => table[_ - 'a']++);
    b.ToList().ForEach(_ => table[_ - 'a']--);

    return table.Sum(_ => Math.Abs(_));
}
```
