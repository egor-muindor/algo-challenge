# Subsets

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

## Description

<div><p>Given a set of <strong>distinct</strong> integers, <em>nums</em>, return all possible subsets (the power set).</p>

<p><strong>Note:</strong> The solution set must not contain duplicate subsets.</p>

<p><strong>Example:</strong></p>

<pre><strong>Input:</strong> nums = [1,2,3]
<strong>Output:</strong>
[
  [3],
&nbsp; [1],
&nbsp; [2],
&nbsp; [1,2,3],
&nbsp; [1,3],
&nbsp; [2,3],
&nbsp; [1,2],
&nbsp; []
]</pre>
</div>

## Solution code

```go
package main

func subsets(nums []int) (result [][]int) {
	var semiResult []int
	for i := 0; i < (1 << len(nums)); i++ {
		semiResult = []int{}
		for j := 0; j < len(nums); j++ {
			if (i & (1 << j)) > 0 {
				semiResult = append(semiResult, nums[j])
			}
		}
		result = append(result, semiResult)
	}
	
	return
}
```

## Submission Detail

```
10 / 10 test cases passed.
Status: Accepted
Runtime: 0 ms
Memory Usage: 2.3 MB
```

## Links

- [Problem](https://leetcode.com/problems/subsets/)
- [Submission](https://leetcode.com/submissions/detail/410959533/)
