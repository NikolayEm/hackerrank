[Breaking the Records](https://www.hackerrank.com/challenges/breaking-best-and-worst-records/problem)

```csharp
static int[] breakingRecords(int[] scores)
{
    int[] result = new int[2] { 0, 0 };
    int high = scores[0];
    int low = scores[0];

    for (int i = 1; i < scores.Length; i++)
    {
        int c = scores[i];

        if (c > high)
        {
            high = c;
            result[0]++;
        }
        else if (c < low)
        {
            low = c;
            result[1]++;
        }
    }

    return result;
}
```
