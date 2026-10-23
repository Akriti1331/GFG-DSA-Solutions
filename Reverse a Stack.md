## 01. Reverse a Stack

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/reverse-a-stack/1?utm_source=chatgpt.com)

### Problem Description

**Task:** You are given a stack st[]. You have to reverse the stack.

> **Note:** The input array represents the stack from bottom to top (last element is the top). The output is displayed by printing elements from top to bottom after reversal.

#### Examples

##### Example 1

- **Input:**
```text
st[] = [1, 2, 3, 4]Output: [1, 2, 3, 4]Explanation: After reversing, the elements of stack are in opposite order.
```

##### Example 2

- **Input:**
```text
st[] = [3, 2, 1]Output: [3, 2, 1]Explanation: After reversing, the elements of stack are in opposite order.
```

#### Constraints

- **1.** `1 ≤ st.size() ≤ 1000 ≤ stack element ≤ 100`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (2)

#### Solution 1 (C++)

- **Submitted:** 2026-10-24 04:18:04
- **Status:** Correct
- **Marks:** 0

```cpp
class Solution {
  public:
  
    void insertAtBottom(stack<int> &st, int ele) {
        
        //Base case
        if(st.empty()) {
            st.push(ele);
            return;
        }
        
        int num = st.top();
        st.pop();
        
        insertAtBottom(st, ele);
        st.push(num);
    }
    
    void reverseStack(stack<int> &st) {
        
        //Base Case
        if(st.empty()) {
            return;
        }
        
        int num = st.top();
        st.pop();
        
        reverseStack(st);
        insertAtBottom(st, num);
        
    }
};
```

#### Solution 2 (C++)

- **Submitted:** 2026-10-24 03:52:18
- **Status:** Correct
- **Marks:** 4

```cpp
class Solution {
  public:
  
    void insertAtBottom(stack<int> &st, int ele) {
        
        //Base case
        if(st.empty()) {
            st.push(ele);
            return;
        }
        
        int num = st.top();
        st.pop();
        
        insertAtBottom(st, ele);
        st.push(num);
    }
    
    void reverseStack(stack<int> &st) {
        
        //Base Case
        if(st.empty()) {
            return;
        }
        
        int num = st.top();
        st.pop();
        
        reverseStack(st);
        insertAtBottom(st, num);
        
    }
};
```

*Generated on: 24/10/2026, 04:19:19*