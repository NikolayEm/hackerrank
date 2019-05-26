[Minimum Absolute Difference in an Array](https://www.hackerrank.com/challenges/minimum-absolute-difference-in-an-array/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=greedy-algorithms)

## My notes
First solution is pretty straightforward, it's O(n^2), since according the task we need to calc each element with any, the 1st implmentation might be achieved via double looping within the same array, which is very slow and would not pass tests

```csharp
static int minimumAbsoluteDifference(int[] arr)
{
    int result = int.MaxValue;

    for(int i = 0; i < arr.Length - 1; i++)
    {
        int left = arr[i];

        for(int j = 0; j < arr.Length; j++)
        {
            if (i == j)
            {
                continue;
            }

            int right = arr[j];

            int delta = Math.Abs(left - right);

            if (delta < result)
            {
                result = delta;
            }
        }
    }

    return result;
}
```

### 2nd solution - O(n^2) reduced to O(n), achieved by sorting step
```csharp
static int minimumAbsoluteDifference(int[] arr)
{
    int result = int.MaxValue;

    Array.Sort(arr);

    for(int i = 0; i < arr.Length - 1; i++)
    {
        int left = arr[i];

        int right = arr[i + 1];

        int delta = Math.Abs(left - right);

        if (delta < result)
        {
            result = delta;
        }
    }

    return result;
}
```