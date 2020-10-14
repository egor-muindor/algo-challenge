# Valid Palindrome

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

## Description

<div><p>Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.</p>

<p><strong>Note:</strong>&nbsp;For the purpose of this problem, we define empty string as valid palindrome.</p>

<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> "A man, a plan, a canal: Panama"
<strong>Output:</strong> true
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> "race a car"
<strong>Output:</strong> false
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>s</code> consists only of printable ASCII characters.</li>
</ul>
</div>

## Solution code

```go
package main

import (
	"strings"
)

func isPalindrome(s string) bool {
	s = strings.ToLower(s)
	for i, j := 0, len(s)-1; i < j; {
		if !strings.Contains("abcdefghijklmnopqrstuvwxyz0123456789", string(s[i])) {
			i++
			continue
		}
		if !strings.Contains("abcdefghijklmnopqrstuvwxyz0123456789", string(s[j])) {
			j--
			continue
		}
		if s[i] != s[j] {
			return false
		}
		i++
		j--
	}
	return true
}
```

## Submission Detail

```
481 / 481 test cases passed.
Status: Accepted
Runtime: 4 ms
Memory Usage: 2.9 MB
```

## Links

- [Problem](https://leetcode.com/problems/valid-palindrome/)
- [Submission](https://leetcode.com/submissions/detail/408585715/)
