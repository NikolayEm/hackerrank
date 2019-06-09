[Strong Password](https://www.hackerrank.com/challenges/strong-password/problem)

```csharp
static int minimumNumber(int n, string password)
{
    var buffer = new int[4] { 1, 1, 1, 1 };

    foreach(char c in password)
    {
        if (char.IsNumber(c))
        {
            buffer[0] = 0;
        }
        else if (char.IsLower(c))
        {
            buffer[1] = 0;
        }
        else if (char.IsUpper(c))
        {
            buffer[2] = 0;
        }
        else if ("!@#$%^&*()-+".Contains(c))
        {
            buffer[3] = 0;
        }
    }

    return Math.Max(buffer.Sum(), 6 - password.Length);
}
```