# Running Sum of 1d Array

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

## Description

Given an array nums. We define a running sum of an array as runningSum[i] = sum(nums[0]…nums[i]).

Return the running sum of nums.{desc}

## Solution code

```go
package main

func runningSum(nums []int) []int {
	r := make([]int, len(nums))
	for i, v := range nums {
		if i > 0 {
			r[i] = r[i-1] + v
		} else {
			r[i] = v
		}
	}
	return r
}
```

## Submission Detail

```
Runtime 3 ms | Beats 72.54%
Memory 2.8 MB | Beats 47.46%
```

## Links

- [Problem](https://leetcode.com/problems/running-sum-of-1d-array/)
- [Submission](https://leetcode.com/problems/running-sum-of-1d-array/submissions/850246112/)
