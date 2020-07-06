*I can tell it's EASIER than any past problems, weird! I didn't even write an 'solve' function...*
```python
T = int(input())
for t in range(1, T+1):
    N = int(input())
    res = 0
    nums = [int(x) for x in input().split()]
    for i in range(1, N-1):
        if nums[i] > nums[i-1] and nums[i] > nums[i+1]:
            res += 1
    print("Case #{}: {}".format(t, res))
```
