[Hash Tables: Ransom Note](https://www.hackerrank.com/challenges/ctci-ransom-note/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=dictionaries-hashmaps)

```csharp
static void checkMagazine(string[] magazine, string[] note)
{
    var sets = new Dictionary<string, int>(magazine.OrderBy(w => w).GroupBy(w => w).ToDictionary(e => e.Key, e => e.Count()));

    foreach(string word in note)
    {
        if (!sets.ContainsKey(word) || sets[word] == 0)
        {
            Console.WriteLine("No");
            return;
        }

        sets[word]--;
    }

    Console.WriteLine("Yes");
}
```
