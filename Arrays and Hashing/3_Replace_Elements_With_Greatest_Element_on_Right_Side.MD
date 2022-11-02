**APPROACH :**

* **```Step 1:```** Iterate from the back to the start or reverse,
* **```Step 2:```** We initilize ```mx = -1```, where mx represent the max on the right.
* **```Step 3:```** Each round, we set ````A[i] = mx```, where mx is its mas on the right.
* **```Step 4:```** Also we update ```mx = max(mx, A[i])```, where A[i] is its original value.


**NOTE(CPP) :**

The ```exchange()``` function is a built-in function in ```C++ 14``` defined in the ```<utility>``` header. The exchange() function copies new value to old value and it will return the old value.<br>

**Syntax:**

```cpp
exchange(old, new)
```

**NOTE(PYTHON) :**

* ```range()``` – This returns a range object (a type of iterable).
* ```xrange()``` – This function returns the generator object that can be used to display numbers only by looping. The only particular range is displayed on demand and hence called “lazy evaluation“.

<hr>

**CPP SOLUTION :**

```cpp
class Solution {
public:
    vector<int> replaceElements(vector<int>& arr, int mx = -1) {
        int sz = arr.size();
        for(int i = sz-1;i>=0;i--){
            mx = max(mx, exchange(arr[i],mx));
        }
        return arr;
    }
};
```

<hr>

**PYTHON SOLUTION :**

```py
class Solution(object):
    def replaceElements(self, arr, mx = -1):
        """
        :type arr: List[int]
        :rtype: List[int]
        """
        x = len(arr)
        for i in range(x-1,-1,-1):
            arr[i], mx = mx, max(mx, arr[i])
        return arr
```

<hr>

**Complexity**
```
Time: O(N)
Space: O(1)
```
