## Print this pattern for nth term
* Input1: `n=4`\
Output:
```
1      1
12    21
123  321
12344321
```
* Input2: `n=6`\
Output:
```
1          1
12        21
123      321
1234    4321
12345  54321
123456654321
```
> The below code only works for single digit 'n', in future i ll update this code for general input

**Code:**
```python
n = 6
space = 2*n-2
for i in range(1,n+1):
    a = []
    for j in range(i):
        a.append(j+1)
    rev = sorted(a,reverse=True)
    print(*a,space*" ",*rev,end="",sep="")
    print()
    space -= 2
```
## I hope you liked the code :smiley:
