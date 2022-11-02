**What is Anagram?** <br>
An anagram of a string is another string that contains the same characters, only the order of characters can be different. For example, “abcd” and “dabc” are an anagram of each other. <br>

**Example 1:**
```
Input: s = "anagram", t = "nagaram"
Output: true
```

**Example 2:**
```
Input: s = "rat", t = "car"
Output: false
```
 

**Constraints:**

* **1 <= s.length, t.length <= 5 * 10<sup>4</sup>**
* ```s``` and ```t``` consist of lowercase English letters.


**Approach** <br>

* **```Step 1:```** Sort both strings.
* **```Step2:```** Compare the sorted strings: 
    * If they are equal return True.
    * Else return False.

<hr>

```cpp
#define all(x) (x).begin(),(x).end()
#define r return
#define ff false
#define tt true
class Solution {
public:
    bool isAnagram(string s, string t) {
        int n1 = s.size();
        int n2 = t.size();
        if(n1 != n2) r ff;
        sort(all(s));
        sort(all(t));
        for(int i=0;i<n1;i++){
            if(s[i] != t[i]) r ff;
        }
        r tt;
    }
};
```

<hr>

```py

class Solution(object):
    def isAnagram(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """
        if len(s) != len(t):
            return False
        s = sorted(s)
        t = sorted(t)
        for i in range(len(s)):
            if s[i] != t[i]:
                return False
        return True
```