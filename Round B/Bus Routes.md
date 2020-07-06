```python
def solve(nums, N, D):
    lday = D
    for n in nums[::-1]:
        tmp = n
        lday -= lday%n
    return lday

T = int(input())
for t in range(1, T+1):
    N, D = map(int, input().split())
    nums = [int(x) for x in input().split()]
    print("Case #{}: {}".format(t, solve(nums, N, D)))
```
