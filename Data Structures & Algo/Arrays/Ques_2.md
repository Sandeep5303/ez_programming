## Reverse upto nth term in a list without slicing
For example
* Input1:
`li = [2, 3, 5, 4, 5, 2]`\
`n = 5`\
output: `[5, 4, 5, 3, 2, 2]`

* Input2:
`li = [2, 3, 5, 4, 5, 2]`\
`n = 3`\
output: `[5, 3, 2, 4, 5, 2]`

```python
def reverse(x, n, k = 0):
    for i in range(n-1,0,-1):
        x[i], x[k] = x[k], x[i] # swapping nth value with first value and so on
        k += 1
        if k == n//2: # for given nth term, swapping will occur n//2(floor value) times only
            break

    return x
#client code
li = [2, 3, 5, 4, 5, 2]
n = 3
print(reverse(li,n))
```

## I hope you liked the code!!:smiley:
