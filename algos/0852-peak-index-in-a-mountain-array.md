# Peak Index in a Mountain Array

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

## Description

<div><p>Let's call an array <code>arr</code> a <strong>mountain</strong>&nbsp;if the following properties hold:</p>

<ul>
	<li><code>arr.length &gt;= 3</code></li>
	<li>There exists some <code>i</code> with&nbsp;<code>0 &lt; i&nbsp;&lt; arr.length - 1</code>&nbsp;such that:
	<ul>
		<li><code>arr[0] &lt; arr[1] &lt; ... arr[i-1] &lt; arr[i] </code></li>
		<li><code>arr[i] &gt; arr[i+1] &gt; ... &gt; arr[arr.length - 1]</code></li>
	</ul>
	</li>
</ul>

<p>Given an integer array arr that is <strong>guaranteed</strong> to be&nbsp;a mountain, return any&nbsp;<code>i</code>&nbsp;such that&nbsp;<code>arr[0] &lt; arr[1] &lt; ... arr[i - 1] &lt; arr[i] &gt; arr[i + 1] &gt; ... &gt; arr[arr.length - 1]</code>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<pre><strong>Input:</strong> arr = [0,1,0]
<strong>Output:</strong> 1
</pre><p><strong>Example 2:</strong></p>
<pre><strong>Input:</strong> arr = [0,2,1,0]
<strong>Output:</strong> 1
</pre><p><strong>Example 3:</strong></p>
<pre><strong>Input:</strong> arr = [0,10,5,2]
<strong>Output:</strong> 1
</pre><p><strong>Example 4:</strong></p>
<pre><strong>Input:</strong> arr = [3,4,5,1]
<strong>Output:</strong> 2
</pre><p><strong>Example 5:</strong></p>
<pre><strong>Input:</strong> arr = [24,69,100,99,79,78,67,36,26,19]
<strong>Output:</strong> 2
</pre>
<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>3 &lt;= arr.length &lt;= 10<sup>4</sup></code></li>
	<li><code>0 &lt;= arr[i] &lt;= 10<sup>6</sup></code></li>
	<li><code>arr</code> is <strong>guaranteed</strong> to be a mountain array.</li>
</ul>
</div>

## Solution code

```go
package main

func peakIndexInMountainArray(arr []int) int {
	var prev int
	for i, v := range arr {
		if v < prev {
			return i-1
		}
		prev = v
	}

	return len(arr)-1
}
```

## Submission Detail

```
34 / 34 test cases passed.
Status: Accepted
Runtime: 8 ms
Memory Usage: 4.8 MB
```

## Links

- [Problem](https://leetcode.com/problems/peak-index-in-a-mountain-array/)
- [Submission](https://leetcode.com/submissions/detail/409365278/)
