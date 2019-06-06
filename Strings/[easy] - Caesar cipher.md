[Caesar Cipher](https://www.hackerrank.com/challenges/caesar-cipher-1/problem)

```csharp
static string caesarCipher(string s, int k)
{
    int step = k % 26;

    char[] buffer = new char[s.Length];

    for (int i = 0; i < s.Length; i++)
    {
        char current = s[i];

        if (char.IsLetter(current))
        {
            int code = current + step;

            if (char.IsLower(current) && code > 'z')
            {
                code = (code - 'z') + 'a' - 1;
            }
            else if (!char.IsLower(current) && code > 'Z')
            {
                code = (code - 'Z') + 'A' - 1;
            }

            buffer[i] = (char) code;
        }
        else
        {
            buffer[i] = current;
        }
    }

    return new string(buffer);
}
```
