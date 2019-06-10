[Funny String](https://www.hackerrank.com/challenges/funny-string/problem)

```csharp
static string funnyString(string s)
{
    int len = s.Length - 1;

    for (int i = 0; i < len; i++)
    {
        int head = Math.Abs(s[i] - s[i + 1]);
        int tail = Math.Abs(s[len - i] - s[len - i - 1]);

        if (head != tail)
        {
            return "Not Funny";
        }
    }

    return "Funny";
}
```