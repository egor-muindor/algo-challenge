### Valid Parentheses

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

#### Description

<div><p>Given a string <code>s</code> containing just the characters <code>'('</code>, <code>')'</code>, <code>'{'</code>, <code>'}'</code>, <code>'['</code> and <code>']'</code>, determine if the input string is valid.</p>

<p>An input string is valid if:</p>

<ol>
	<li>Open brackets must be closed by the same type of brackets.</li>
	<li>Open brackets must be closed in the correct order.</li>
</ol>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> s = "()"
<strong>Output:</strong> true
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> s = "()[]{}"
<strong>Output:</strong> true
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> s = "(]"
<strong>Output:</strong> false
</pre>

<p><strong>Example 4:</strong></p>

<pre><strong>Input:</strong> s = "([)]"
<strong>Output:</strong> false
</pre>

<p><strong>Example 5:</strong></p>

<pre><strong>Input:</strong> s = "{[]}"
<strong>Output:</strong> true
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= s.length &lt;= 10<sup>4</sup></code></li>
	<li><code>s</code> consists of parentheses only <code>'()[]{}'</code>.</li>
</ul>
</div>

#### Solution code

```go
package main

import s "strings"

func isValid(str string) bool {
    var o_brackets []byte
    if str == "" {
        return true
    }
    for _, v := range []byte(str) {
        if s.Contains("{[(", string(v)) {
            o_brackets = append(o_brackets, v)
            continue
        } else {
            if len(o_brackets) == 0 {
                return false
            }
            switch last := o_brackets[len(o_brackets)-1]; v {
            case '}':
                if last == '{' {
                    o_brackets = o_brackets[:len(o_brackets)-1] 
                    continue
                } else {
                    return false
                }
            case ']':
                if last == '[' {
                    o_brackets = o_brackets[:len(o_brackets)-1]
                    continue
                } else {
                    return false
                }

            case ')':
                if last == '(' {
                    o_brackets = o_brackets[:len(o_brackets)-1]
                    continue
                } else {
                    return false
                }

            default:
                return false
            }
        }
    }
    if len(o_brackets) > 0 {
        return false
    }
    return true
}
```

#### Submission Detail

```
91 / 91 test cases passed.
Status: Accepted
Runtime: 0 ms
Memory Usage: 2 MB
```

#### Links

- [Problem](https://leetcode.com/problems/valid-parentheses/)
- [Submission](https://leetcode.com/submissions/detail/403508953/)

