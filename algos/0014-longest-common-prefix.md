# Longest Common Prefix

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

## Description

<div><p>Write a function to find the longest common prefix string amongst an array of strings.</p>

<p>If there is no common prefix, return an empty string <code>""</code>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> strs = ["flower","flow","flight"]
<strong>Output:</strong> "fl"
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> strs = ["dog","racecar","car"]
<strong>Output:</strong> ""
<strong>Explanation:</strong> There is no common prefix among the input strings.
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>0 &lt;= strs.length &lt;= 200</code></li>
	<li><code>0 &lt;= strs[i].length &lt;= 200</code></li>
	<li><code>strs[i]</code> consists of only lower-case English letters.</li>
</ul>
</div>

## Solution code

```go
package main

func longestCommonPrefix(strs []string) string {
	var longestPrefix string
	if len(strs) == 0 {
		return ""
	}
	if len(strs) == 1 {
		return strs[0]
	}
	longestPrefix = strs[0]
	for _, v := range strs[1:] {
		if longestPrefix == "" {
			break
		}
		if len(longestPrefix) < len(v) {
			if v[:len(longestPrefix)] == longestPrefix {
				continue
			}
		} else {
			if v == longestPrefix[:len(v)] {
				longestPrefix = v
				continue
			}
		}
		for i := 0; i < len(longestPrefix) && i < len(v); i++ {
			if v[i] != longestPrefix[i] {
				longestPrefix = longestPrefix[:i]
			}
		}
	}

	return longestPrefix
}
```

## Submission Detail

```
123 / 123 test cases passed.
Status: Accepted
Runtime: 0 ms
Memory Usage: 2.4 MB
```

## Links

- [Problem](https://leetcode.com/problems/longest-common-prefix/)
- [Submission](https://leetcode.com/submissions/detail/406975010/)
