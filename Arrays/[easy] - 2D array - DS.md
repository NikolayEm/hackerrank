[2D Array - DS](https://www.hackerrank.com/challenges/2d-array/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=arrays)

```csharp
static int hourglassSum(int[][] arr)
{
    int result = int.MinValue;
    int delta = 0;

    for (int i = 0; i <= arr.Length - 3; i++)
    {
        int row1 = arr[i];
        int row2 = arr[i + 1];
        int row3 = arr[i + 2];

        for (int j = 0; j <= arr.Length - 3; j++)
        {
            int sum1 = row1.Skip(j).Take(3).Sum();
            int sum2 = row2.Skip(j + 1).Take(1).Sum();
            int sum3 = row3.Skip(j).Take(3).Sum();

            delta = sum1 + sum2 + sum3;

            result = Math.Max(delta, result);
        }
    }

    return result;
}
```