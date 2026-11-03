## 01. Check Redundant Brackets

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/expression-contains-redundant-bracket-or-not/1?utm_source=chatgpt.com)

### Problem Description

**Task:** Given a string of balanced expression s, check if it contains a redundant parenthesis or not. A set of parenthesis are redundant if the same sub-expression is surrounded by unnecessary or multiple brackets.Note: Expression may contain + , - , *, and / operators. Given expression is valid and there are no white spaces present.Examples:

#### Examples

##### Example 1

- **Input:**
```text
s = "((a+b))"
```
- **Output:**
```text
true
```
- **Explanation:** ((a+b)) can reduced to (a+b).

##### Example 2

- **Input:**
```text
s = "(a+(b)/c)"
```
- **Output:**
```text
true
```
- **Explanation:** (a+(b)/c) can reduced to (a+b/c) because b is surrounded by () which is redundant.

##### Example 3

- **Input:**
```text
s = "(a+b+(c+d))"
```
- **Output:**
```text
false
```
- **Explanation:** (a+b+(c+d)) doesn't have any redundant or multiple brackets.

#### Constraints

- **1.** `1 ≤ |s| ≤10⁵`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-11-04 00:38:02
- **Status:** Correct
- **Marks:** 4

```cpp
#include<stack>

class Solution {
  public:
    bool checkRedundancy(string &s) {
        
        stack<char> st;
        for(int i = 0; i < s.length(); i++) {
            char ch = s[i];
            
            if(ch == '(' || ch == '+' || ch == '-' || ch == '*' || ch == '/') {
                st.push(ch);
            }
            
            else {
                
                if(ch == ')') {
                    bool isRedundant = true;
                    
                    while(st.top() != '(') {
                        char top = st.top();
                        if(top == '+' || top == '-' || top == '*' || top == '/') {
                            isRedundant = false;
                        }
                        st.pop();
                    }
                    
                    if(isRedundant == true) {
                        return true;
                    }
                    
                    st.pop();
                }
            }
        }
        return false;
    }
};
```

*Generated on: 04/11/2026, 00:38:47*