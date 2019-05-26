[Alternating Characters](https://www.hackerrank.com/challenges/alternating-characters/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=strings)


```csharp
static int alternatingCharacters(string s)
{
    int counter = 0;

    for(int i = 0; i < s.Length - 1; i++)
    {
        char left = s[i];
        char right = s[i + 1];
        if (left == right)
        {
            counter++;
        }
    }

    return counter;
}
```
