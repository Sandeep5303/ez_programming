## Print the pattern for nth term
* Input1: `n = 4`\
Ouput:
```
1
11
21
1211
```
* Input1: `n = 6`\
Ouput:
```
1
11
21
1211
111221
312221
```
### Please try to implement yourself before reading the logic and code

* Logic:
``` 
Here n depicts number of rows to print, The pattern always start from 1. The succeeding row always
depends on preceeding row. The succeeding row counts the number of occurences of a number and prints it
For example:
if n = 3
pattern should be
1
11
21
Here the first row starts with 1 then in the second row it counts the number of times 1 occurs,
it occured 1 time so output is 1(count)1(number)
In the third row it counts the number of times 1 occurs again,
1 occurred 2 times so output is 2(count)1(number)
```
* Note:
> the count is counted untill different number is found. For example 111221, the next output will be 312211 not 4122 because after
> 111 another number 2 is found which different from 1

```python
def code(b):
    res = ''
    c = 1
    if len(b) == 1:
        res = str(c) + b
    else:
        for i in range(len(b)-1):
            if b[i] == b[i+1]:
                c += 1
            else:
                res = res + str(c) + b[i]
                c = 1
            if i == len(b)-2 and b[len(b)-1] != b[len(b)-2]: # if we are at second last element and second last element is not equals to last element
                res = res + str(c) + b[i + 1]
            elif i == len(b)-2 and b[len(b)-1] == b[len(b)-2]: # if we are at second last element and second last element is equals to last element
                res = res + str(c) + b[i]

    return res

def pattern(n):
    old = ""
    for i in range(1, n+1):
        if i == 1:
            old = str(i) # storing 1 in old for i = 1
            print(old)
        else:
            old = code(old)
            print(old)

n = 4
pattern(n)
```

## I hope you liked the code :smiley:
 
