# Happy Number

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

## Description

<div><p>Write an algorithm to determine if a number <code>n</code> is "happy".</p>

<p>A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it <strong>loops endlessly in a cycle</strong> which does not include 1. Those numbers for which this process <strong>ends in 1</strong> are happy numbers.</p>

<p>Return True if <code>n</code> is a happy number, and False if not.</p>

<p><strong>Example:&nbsp;</strong></p>

<pre><strong>Input:</strong> 19
<strong>Output:</strong> true
<strong>Explanation:
</strong>1<sup>2</sup> + 9<sup>2</sup> = 82
8<sup>2</sup> + 2<sup>2</sup> = 68
6<sup>2</sup> + 8<sup>2</sup> = 100
1<sup>2</sup> + 0<sup>2</sup> + 0<sup>2</sup> = 1
</pre>
</div>

## Solution code

```go
package main

func isHappy(n int) bool {
	calculated := make(map[int]bool)
	var tmp int
	for n != 1 {
		if _, ok := calculated[n]; ok {
			return false
		}
		calculated[n] = true
		tmp = 0
		for n > 0 {
			tmp += (n % 10) * (n % 10)
			n = n / 10
		}
		n = tmp
	}

	return true
}
```

## Submission Detail

```
401 / 401 test cases passed.
Status: Accepted
Runtime: 0 ms
Memory Usage: 2.1 MB
```

## Links

- [Problem](https://leetcode.com/problems/happy-number/)
- [Submission](https://leetcode.com/submissions/detail/409012140/)
