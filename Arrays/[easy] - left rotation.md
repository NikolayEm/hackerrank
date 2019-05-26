[Left Rotation](https://www.hackerrank.com/challenges/ctci-array-left-rotation/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=arrays)

```csharp
static int[] rotLeft(int[] a, int d)
{
    var result = new List<int>();

    int offset = a.Length - 1 - d;

    int start = a.Take(d).ToArray();
    int end = a.Skip(d).ToArray();

    result.AddRange(end);
    result.AddRange(start);

    return result.ToArray();
}
```