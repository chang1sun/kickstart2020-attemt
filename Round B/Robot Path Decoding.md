***I only get an AC on first dataset cause I can't find where the numeric bug is even I noticed the overflow error. Sad, wasted tons of time!!***
```python
def solve(s):
    r, d = 0, 0
    stack = []
    muti = 1
    mod = 1000000000
    for i, c in enumerate(s):
        if c == '(':
            stack.append(s[i-1])
            muti = ((muti+mod)*(int(stack[-1])+mod)) % mod
        elif c == ')':
            muti = int(muti/int(stack.pop()))
        elif ord(c)>64:
            if c == 'N':
                d = (d - muti + mod) % mod
            elif c == 'S':
                d = (d + muti + mod) % mod
            elif c == 'W':
                r = (r - muti + mod) % mod
            else:
                r = (r + muti + mod) % mod
    return [r+1, d+1]
T = int(input())
for t in range(1, T+1):
    s = input()
    print("Case #{}: {}".format(t, " ".join(map(str, solve(s)))))
```
