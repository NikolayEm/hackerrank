[Apple and Orange](https://www.hackerrank.com/challenges/apple-and-orange/problem)

## Explicit implementation
```csharp
static void countApplesAndOranges(int s, int t, int a, int b, int[] apples, int[] oranges)
{
    int applesCount = 0;
    int orangesCount = 0;

    for (int i = 0; i < apples.Length; i++)
    {
        int pos = a + apples[i];

        if (pos >= s && pos <= t)
        {
            applesCount++;
        }
    }

    for (int i = 0; i < oranges.Length; i++)
    {
        int pos = b + oranges[i];

        if (pos >= s && pos <= t)
        {
            orangesCount++;
        }
    }

    Console.WriteLine(applesCount);
    Console.WriteLine(orangesCount);
}
```

## LINQ implementation
```csharp
static void countApplesAndOranges(int s, int t, int a, int b, int[] apples, int[] oranges)
{
    Console.WriteLine(apples.Where(i => a + i >= s && a + i <= t).Count());
    Console.WriteLine(oranges.Where(i => b + i >= s && b + i <= t).Count());
}
```