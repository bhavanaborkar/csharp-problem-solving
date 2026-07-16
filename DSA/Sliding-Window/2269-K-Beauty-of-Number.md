
# LeetCode 2269 - Find the K-Beauty of a Number

## Problem Pattern

Fixed Sliding Window

---

## Problem Understanding

Given an integer num and window size k,
find how many k-length substrings divide the original number.

Example:

Input:
num = 240, k = 2

Windows:

24
40

Both divide 240.

Answer = 2

---

## Approach

1. Convert number to string.
2. Use two pointers:
   - i = left pointer
   - j = right pointer
3. Maintain window size k.
4. Check if current window divides the number.

---

## Solution

```csharp
public int DivisorSubstrings(int num, int k)
{
    string s = num.ToString();

    int i = 0;
    int j = 0;
    int count = 0;

    while(j < s.Length)
    {
        if(j - i + 1 < k){
                j++;
        }
            else if( j - i + 1 == k){
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
