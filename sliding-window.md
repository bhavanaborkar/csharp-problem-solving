```csharp
/* Leetcode : 2269 -> Find the K-Beauty of a Number */

public int DivisorSubstrings(int num, int k) 
{
    int i = 0, j = 0;
    int count = 0;

    string s = num.ToString();

    while(j < s.Length)
    {
        if(j - i + 1 < k)
        {
            j++;
        }
        else if(j - i + 1 == k)
        {
            string window = s.Substring(i, k);
            int divisor = int.Parse(window);

            if(divisor != 0 && num % divisor == 0)
            {
                count++;
            }

            i++;
            j++;
        }
    }

    return count;
}
```
