[Count Triplets](https://www.hackerrank.com/challenges/count-triplets-1/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=dictionaries-hashmaps)

```csharp
static long countTriplets(List<long> arr, long r)
{
//copied https://www.hackerrank.com/challenges/count-triplets-1/forum/comments/487893
    var mp2 = new Dictionary<long, long>();
    var mp3 = new Dictionary<long, long>();

    long res = 0;

    foreach (long val in arr)
    {
        if (mp3.ContainsKey(val))
        {
            res += mp3[val];
        }

        if (mp2.ContainsKey(val))
        {
            if (mp3.ContainsKey(val * r))
            {
                mp3[val * r] += mp2[val];
            }
            else
            {
                mp3[val * r] = mp2[val];
            }
        }

        if (mp2.ContainsKey(val * r))
        {
            mp2[val * r]++;
        }
        else
        {
            mp2[val * r] = 1;
        }
    }

    return res;
}
```
