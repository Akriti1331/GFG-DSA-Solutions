## 01. Insert at Bottom of Stack

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/insert-an-element-at-the-bottom-of-a-stack/1?utm_source=chatgpt.com)

### Problem Description

**Task:** Given a stack st containing n integers and an integer x, insert x at the bottom of the stack.

> **Note:** While displaying the stack, the bottommost element is printed first.

#### Examples

##### Example 1

- **Input:**
```text
st = [4, 3, 2, 1, 8], x = 2
```
- **Output:**
```text
[2, 4, 3, 2, 1, 8]
```
- **Explanation:** After insertion of 2, the final stack will be [2,4,3,2,1,8].

##### Example 2

- **Input:**
```text
st = [5, 3, 1], x = 4
```
- **Output:**
```text
[4, 5, 3, 1]
```
- **Explanation:** After insertion of 4, the final stack will be [4,5,3,1].

#### Constraints

- **1.** `1 ≤ n ≤ 10⁵⁰ ≤ x, elements of stack ≤ 10⁹`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-10-24 16:32:59
- **Status:** Correct
- **Marks:** 2

```cpp
class Solution {
  public:
  
    void solve(stack<int> &st, int num) {
        
        //Base case
        if(st.empty()) {
            st.push(num);
            return;
        }
        
        int ele = st.top();
        st.pop();
        
        solve(st, num);
        st.push(ele);
    }
    
    stack<int> insertAtBottom(stack<int> &st, int x) {
        
        solve(st, x);
        return st;
        
    }
};
```

*Generated on: 24/10/2026, 16:42:23*