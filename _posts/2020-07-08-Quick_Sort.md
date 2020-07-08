---
layout: default
title: "Quick_Sort"
tags: algorithm
---

# Quick_Sort(수정 중)



대부분의 퀵소트의 경우 pivot 값을 기준으로 좌우 리스트를 정한다.

이 경우 메모리 낭비가 심하다고 생각해(필자는 깔끔한 것을 좋아함) 리스트를 따로 만들지 않고

인덱스 접근으로 풀어보았다.





**Python 코드**

```python
def partition(left, right):

    pivot = nums[(left+right)//2]

    while left <= right:
        while nums[left] < pivot:
            left += 1
        while nums[right] > pivot:
            right -= 1

        if right >= left:
            nums[left], nums[right] = nums[right], nums[left]
            left += 1
            right -= 1

    return left


def Q_Sort(left, right):
    if left >= right:
        return

    mid = partition(left, right)
    Q_Sort(left, mid - 1)
    Q_Sort(mid, right)


N = 10
nums = [4,2,7,8,3,5,9,1,6,0]
Q_Sort(0, N-1)

print(nums)
```
