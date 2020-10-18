# Count Primes

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

## Description

<div><p>Count the number of prime numbers less than a non-negative number, <code>n</code>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> n = 10
<strong>Output:</strong> 4
<strong>Explanation:</strong> There are 4 prime numbers less than 10, they are 2, 3, 5, 7.
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> n = 0
<strong>Output:</strong> 0
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> n = 1
<strong>Output:</strong> 0
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>0 &lt;= n &lt;= 5 * 10<sup>6</sup></code></li>
</ul>
</div>

## Solution code

```go
package main

func countPrimes(n int) (count int) {
	if n < 2 {
		return 0
	}
	primes := make([]bool, n)
	for i := 0; i < n; i++ {
		primes[i] = true
	}
	primes[0], primes[1] = false, false
	for i := 2; i*i < n; i++ {
		if primes[i] {
			for j := i * i; j < n; j += i {
				primes[j] = false
			}
		}
	}
	for _, v := range primes {
		if v {
			count++
		}
	}
	return
}
```

## Submission Detail

```
20 / 20 test cases passed.
Status: Accepted
Runtime: 4 ms
Memory Usage: 4.9 MB
```

## Links

- [Problem](https://leetcode.com/problems/count-primes/)
- [Submission](https://leetcode.com/submissions/detail/410179848/)
