[Extra Long Factorials](https://www.hackerrank.com/challenges/extra-long-factorials/problem?h_r=profile)

```csharp
static void extraLongFactorials(int n) 
{
    var answer = new System.Numerics.BigInteger(1);

    for (; n > 0; n--)
    {
        answer = System.Numerics.BigInteger.Multiply(answer, n);
    }

    Console.WriteLine(answer);
}
```