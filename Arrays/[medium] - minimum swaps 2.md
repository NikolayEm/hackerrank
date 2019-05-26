[Minimum Swaps 2](https://www.hackerrank.com/challenges/minimum-swaps-2/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=arrays)

```csharp
static int minimumSwaps(int[] arr)
{
    int swaps = 0;

    for (int i = 0; i < arr.Length - 1;)
    {
        int val = arr[i];

        if (val == (i + 1))
        {
            i++;
            continue;
        }

        int ex = arr[val - 1];

        arr[i] = ex;
        arr[val - 1] = val;
        swaps++;
    }

    return swaps;
}
```