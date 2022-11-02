**What is Subsequence?**

```
A subsequence of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., "ace" is a subsequence of "abcde" while "aec" is not).
```

**Example 1:**
```
Input: s = "abc", t = "ahbgdc"
Output: true
```

**Example 2:**
```
Input: s = "axc", t = "ahbgdc"
Output: false
```
 

**Constraints:**

* 0 <= s.length <= 100
* 0 <= t.length <= 10<sup>4</sup>
* ```s``` and ```t``` consist only of lowercase English letters.

<hr>

**APPROACH :**

***TWO POINTER APPROACH[ITERATIVE]***

```
The idea is to use two pointers, one pointer will start from start of str1 and another will start from start of str2. If current character on both the indexes are same then increment both pointers otherwise increment the pointer which is pointing str2.
```

***PseudoCode :***

Follow the steps below to solve the problem:

* Initialize the pointers i and j with zero, where i is the pointer to str1 and j is the pointer to str2.
* If str1[i] = str2[j] then increment both i and j by 1.
* Otherwise, increment only j by 1.
* If i reaches the end of str1 then return TRUE else return FALSE.

<hr>

**CPP**

```cpp
class Solution {
public:
    bool isSubsequence(string s, string t) {
        int size_of_s = s.size();
        int size_of_t = t.size();
        int iterator_of_s = 0;
        int iterator_of_t = 0;
        while((iterator_of_s < size_of_s) and (iterator_of_t < size_of_t)){
            if(s[iterator_of_s] == t[iterator_of_t]){
                iterator_of_s++;
            }
            iterator_of_t++;
        }
        return (iterator_of_s == size_of_s);
    }
};
```

**Python**

```python
class Solution(object):
    def isSubsequence(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """
        size_of_s = len(s)
        size_of_t = len(t)
        iterator_of_s, iterator_of_t = 0, 0
        while((iterator_of_s < size_of_s) and (iterator_of_t < size_of_t)):
            if(s[iterator_of_s] == t[iterator_of_t]):
                iterator_of_s+=1
            iterator_of_t+=1
        return (iterator_of_s == size_of_s)    
```

<hr>

***COMPLEXITY :***

* **Time Complexity :** O(n) 
* **Space Complexity :** O(1)

<hr>