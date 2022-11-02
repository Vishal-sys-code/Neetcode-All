Given a string s consisting of words and spaces, return the length of the last word in the string.

A word is a maximal substring consisting of non-space characters only.

 

**Example 1:**

```
Input: s = "Hello World"
Output: 5
Explanation: The last word is "World" with length 5.
```

**Example 2:**
```
Input: s = "   fly me   to   the moon  "
Output: 4
Explanation: The last word is "moon" with length 4.
```

**Example 3:**

```
Input: s = "luffy is still joyboy"
Output: 6
Explanation: The last word is "joyboy" with length 
6.
``` 

**Constraints:**

* 1 <= s.length <= 10<sup>4</sup>
* ```s``` consists of only English letters and spaces ' '.
* There will be at least one word in ```s```.

<hr>

**CPP**

```cpp
class Solution {
public:
    int lengthOfLastWord(string s) {
        int ans = 0;
        int size_of_string = s.size();
        for(int i = size_of_string-1;i>=0;--i){
            if(s[i] == ' ' and ans>0) return ans;
            if(s[i] != ' ') ans++;
        }
        return ans;
    }
};
```

**Python**

```python
class Solution:
    def lengthOfLastWord(self, s: str) -> int:
        ans = 0
        for i in range(len(s)-1,-1,-1):
            if s[i] == ' ' and ans>0:
                return ans
            if s[i] != ' ':
                ans+=1
        return ans
```

<hr>