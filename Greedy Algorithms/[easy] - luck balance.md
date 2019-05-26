[Luck Balance](https://www.hackerrank.com/challenges/luck-balance/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=greedy-algorithms)

```csharp
static int luckBalance(int k, int[][] contests)
{
    int result = contests.Where(_ => _[1] == 0).Sum(_ => _[0]);

    int[] important = contests.Where(_ => _[1] == 1).Select(_ => _[0]).OrderByDescending(_ => _).ToArray();

    result += important.Take(k).Sum() - important.Skip(k).Sum();

    return result;
}
```
