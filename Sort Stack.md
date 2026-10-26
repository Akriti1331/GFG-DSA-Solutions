## 01. Sort Stack

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/sort-a-stack/1?utm_source=chatgpt.com)

### Problem Description

**Task:** Given a stack of integers st[]. Sort the stack in ascending order (smallest element at the bottom and largest at the top).Examples:Input: st[] = [41, 3, 32, 2, 11]Output: [41, 32, 11, 3, 2]Explanation: After sorting, the smallest element (2) is at the bottom and the largest element (41) is at the top.Input: st[] = [3, 2, 1]Output: [3, 2, 1]Explanation: The stack is already sorted in ascending order.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n^2)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-27 02:03:14
- **Status:** Correct
- **Marks:** 4

```cpp
class Solution {
  public:
    void sortedInsert(stack<int> &st, int num) {
        //Base case
        if(st.empty() || (!st.empty() && st.top() < num)) {
            st.push(num);
            return;
        }
        
        int n = st.top();
        st.pop();
        
        //Recursive call
        sortedInsert(st, num);
        st.push(n);
    }
  
    void sortStack(stack<int> &st) {
        //Base Case
        if(st.empty()) {
            return;
        }
        
        int num = st.top();
        st.pop();
        
        //Recursive call
        sortStack(st);
        sortedInsert(st, num);
    }
};
```

*Generated on: 27/10/2026, 02:03:57*