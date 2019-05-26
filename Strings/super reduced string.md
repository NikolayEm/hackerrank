[Super Reduced String](https://www.hackerrank.com/challenges/reduced-string/problem)

Category - <b>easy</b>


```csharp
static string superReducedString(string s)
{
    var list = new List<char>();

    for (int i = 0; i < s.Length; i++)
    {
        char current = s[i];

        if (list.LastOrDefault() == current)
        {
            list.RemoveAt(list.Count - 1);
        }
        else
        {
            list.Add(current);
        }
    }

    return list.Any() ? new string(list.ToArray()) : "Empty String";
}
```
