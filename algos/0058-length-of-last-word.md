# Length of Last Word

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

## Description

<div><p>Given a string <i>s</i> consists of upper/lower-case alphabets and empty space characters <code>' '</code>, return the length of last word (last word means the last appearing word if we loop from left to right) in the string.</p>

<p>If the last word does not exist, return 0.</p>

<p><b>Note:</b> A word is defined as a <strong>maximal substring</strong> consisting&nbsp;of non-space characters only.</p>

<p><b>Example:</b></p>

<pre><b>Input:</b> "Hello World"
<b>Output:</b> 5
</pre>

<p>&nbsp;</p>
</div>

## Solution code

```go
package main

func lengthOfLastWord(s string) int {
	length := 0
	lastWord := 0
	for _, v := range s {
		if v == ' ' {
			if length == 0 {
				continue
			}
			lastWord = length
			length = 0
			continue
		}
		length++
		lastWord = length
	}
	if lastWord > length {
		return lastWord
	}
	return length
}
```

## Submission Detail

```
59 / 59 test cases passed.
Status: Accepted
Runtime: 0 ms
Memory Usage: 2.1 MB
```

## Links

- [Problem](https://leetcode.com/problems/length-of-last-word/)
- [Submission](https://leetcode.com/submissions/detail/407730153/)
