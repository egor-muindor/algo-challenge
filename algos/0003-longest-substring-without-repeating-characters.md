# Longest Substring Without Repeating Characters

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

## Description

<div><p>Given a string <code>s</code>, find the length of the <b>longest substring</b> without repeating characters.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> s = "abcabcbb"
<strong>Output:</strong> 3
<strong>Explanation:</strong> The answer is "abc", with the length of 3.
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> s = "bbbbb"
<strong>Output:</strong> 1
<strong>Explanation:</strong> The answer is "b", with the length of 1.
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> s = "pwwkew"
<strong>Output:</strong> 3
<strong>Explanation:</strong> The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.
</pre>

<p><strong>Example 4:</strong></p>

<pre><strong>Input:</strong> s = ""
<strong>Output:</strong> 0
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>0 &lt;= s.length &lt;= 5 * 10<sup>4</sup></code></li>
	<li><code>s</code> consists of English letters, digits, symbols and spaces.</li>
</ul>
</div>

## Solution code

```go
package main

func removeLessThan(numbers *map[byte]int, val int) map[byte]int {
	for k, v := range *numbers {
		if v < val {
			delete(*numbers, k)
		}
	}

	return *numbers
}

func lengthOfLongestSubstring(s string) int {
	substring := make(map[byte]int)
	var longest int
	for i, v := range []byte(s) {
		if _, ok := substring[v]; !ok {
			substring[v] = i
		} else {
			removeLessThan(&substring, substring[v])
			substring[v] = i
		}
		if len(substring) > longest {
			longest = len(substring)
		}
	}
	return longest
}
```

## Submission Detail

```
987 / 987 test cases passed.
Status: Accepted
Runtime: 40 ms
Memory Usage: 2.9 MB
```

## Links

- [Problem](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
- [Submission](https://leetcode.com/submissions/detail/404311136/)
