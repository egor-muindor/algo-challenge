# Find Pivot Index

- [Description](#description)
- [Solution code](#solution-code)
- [Submission Detail](#submission-detail)
- [Links](#links)

## Description

Given an array of integers nums, calculate the pivot index of this array.

The pivot index is the index where the sum of all the numbers strictly to the left of the index is equal to the sum of all the numbers strictly to the index's right.

If the index is on the left edge of the array, then the left sum is 0 because there are no elements to the left. This also applies to the right edge of the array.

Return the leftmost pivot index. If no such index exists, return -1.

## Solution code

```go
package main

func pivotIndex(nums []int) int {
	rsum := 0
	for _, v := range nums {
		rsum += v
	}
	lsum := 0
	for i, v := range nums {
		rsum -= v
		if rsum == lsum {
			return i
		}
		lsum += v
	}

	return -1
}
```

## Submission Detail

```
Runtime 21 ms | Beats 89.14%
Memory 6.2 MB | Beats 90.72%
```

## Links

- [Problem](https://leetcode.com/problems/find-pivot-index/)
- [Submission](https://leetcode.com/problems/find-pivot-index/submissions/850285006/)
