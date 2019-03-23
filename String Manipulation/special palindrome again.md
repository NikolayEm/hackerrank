[Special Palindrome Again](https://www.hackerrank.com/challenges/special-palindrome-again/problem?h_l=interview&playlist_slugs%5B%5D=interview-preparation-kit&playlist_slugs%5B%5D=strings)

##My notes
1. String is valid only if 1 character or set of the same characters are in the middle of repeated character. E.g. - aaabbaaa is valid, but aabcaa is not valid;
2. The result at least is equal to string length;

```csharp
static long substrCount(int n, string s)
{
    long result = s.Length;

    for (int i = 0; i < s.Length; i++)
    {
        char current = s[i];

        int offset = 1;

        while (
            (i - offset >= 0) &&                 // not less than string
            (i + offset <= s.Length - 1) &&      // not longer than string
            (s[i - offset] == s[i + offset])     // previous and next are equal
            ) 
        {
            // element before previous and previous are equal
            if (offset > 1)
            {
                if (s[i - offset] != s[i - offset + 1])
                {
                    break;
                }
            }

            result++;
            offset++;
        }

        // repeated string, e.g. aaa
        int repeats = 0;
        while (i + 1 < s.Length && current == s[i + 1])
        {
            repeats++;
            i++;
        }

        result += repeats * (repeats + 1) / 2;
    }

    return result;
}
```
