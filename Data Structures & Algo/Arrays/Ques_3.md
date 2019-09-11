## Given an array, separate positives and negatives and order of appearance of numbers must be maintained

* Input1:
`li = [9,4,-3,-2,1,-1,5,7,-9,-5]`\
Output = `[9, 4, 1, 5, 7, -3, -2, -1, -9, -5]`

* Input2:
`li = [1, -2, 3, -4, 6]`\
Output = `[1, 3, 6, -2, -4]`

```python
def reg(x):
    for i in range(len(x)):
        if x[i] > 0: # if number is +ve then skip
            continue
        else: # if element is -ve
            if i != len(x)-1 and x[i+1] > 0: # if after -ve numbers a +ve number is found then start swaping otherwise search for +ve number
                j = i+1
                while j >= 0 and x[j-1] < 0:
                    x[j], x[j-1] = x[j-1], x[j] # swap the +ve number and -ve number untill the +ve number shifted to left and all the -ve numbers are shifted to right
                    j -= 1
    return x

# Client Code
li = [1, -2, 3, -4, 6]
print(reg(li))
```

### Alternative Approach 
Credits to @Visheshgpt
```python
li = [9,4,-3,-2,1,-1,5,7,-9,-5]
k = len(li)
for i in range(k):
    if li[i] > 0:
        li.append(li[i])
for i in range(k):
    if li[i] < 0:
        li.append(li[i])
print(li[k:])
```

## I hope you liked the code :smiley:
