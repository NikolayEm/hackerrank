[New Year Chaos](https://www.hackerrank.com/challenges/new-year-chaos/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=arrays)

```csharp
static void minimumBribes(int[] q)
{
    int steps = 0;

    var map = new Dictionary<int, int>();
    for (int i = 0; i < q.Length; i++)
    {
        map[q[i]] = i;
    }

    for (int current = q.Length; current > 1; current--)
    {
        int index = map[current];

        int shift = current - index - 1;

        if (shift == 0)
        {
            continue;
        }

        if (shift > 2)
        {
            Console.WriteLine("Too chaotic");
            return;
        }

        for(int address = index; address < index + shift; address++)
        {
            int oldValue = q[address];
            int newValue = q[address + 1];

            q[address] = newValue;
            q[address + 1] = oldValue;

            map[newValue] = address;
            map[oldValue] = address + 1;
        }

        steps += shift;
    }

    Console.WriteLine(steps);
}
```