# Power of Two

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

## Description

<div><p>Given an integer <code>n</code>, write a function to determine if it is a power of two.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> n = 1
<strong>Output:</strong> true
<strong>Explanation: </strong>2<sup>0</sup> = 1
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> n = 16
<strong>Output:</strong> true
<strong>Explanation: </strong>2<sup>4</sup> = 16
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> n = 3
<strong>Output:</strong> false
</pre>

<p><strong>Example 4:</strong></p>

<pre><strong>Input:</strong> n = 4
<strong>Output:</strong> true
</pre>

<p><strong>Example 5:</strong></p>

<pre><strong>Input:</strong> n = 5
<strong>Output:</strong> false
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>-2<sup>31</sup> &lt;= n &lt;= 2<sup>31</sup> - 1</code></li>
</ul>
</div>

## Solution code

```go
package main

import (
	"strconv"
	"strings"
)

func isPowerOfTwo(n int) bool {
	if n < 0 {
		return false
	}
	str := strconv.FormatInt(int64(n), 2)
	return strings.Count(str, "1") == 1
}

```

## Submission Detail

```
1108 / 1108 test cases passed.
Status: Accepted
Runtime: 0 ms
Memory Usage: 2.2 MB
```

## Links

- [Problem](https://leetcode.com/problems/power-of-two/)
- [Submission](https://leetcode.com/submissions/detail/408137472/)
