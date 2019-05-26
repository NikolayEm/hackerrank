[Mars Exploration](https://www.hackerrank.com/challenges/mars-exploration/problem?h_r=profile)

```csharp
static int marsExploration(string s)
{
    const string sample = "SOS";

    int result = s.Where((c, i) => (s[i] != sample[i % 3])).Count();

    return result;

}
```
