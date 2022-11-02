**Approach** <br>
**```Step1 :```** Convert the list or the array into the set because the set do not contain any duplicate value. So the set will discard the duplicate values and obvious it's size should be less than the list/array which was been containing some duplicate values.
**```Step2 :```** Now we will compare the size by ```Size_Of_Set < Size_Of_List_or_Array```. It will give the bool comparision value.

<hr>

**CPP**
```cpp
#include <bits/stdc++.h>
#define si set<int>
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        si s;
        int size_of_array = nums.size();
        s.insert(nums.begin(),nums.end());
        int size_of_set = s.size();
        return size_of_set < size_of_array;
    }
};
```

<hr>

**PYTHON**
```py
class Solution(object):
    def containsDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """
        length_of_list = len(nums)
        s = set(nums)
        length_of_set = len(s)
        return length_of_set<length_of_list     
```