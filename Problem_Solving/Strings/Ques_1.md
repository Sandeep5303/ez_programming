##  Return True if item is list matches all the characters of string 's' except 1 character
For example
* Input1:\
`li = ["orange","apple","banaba"]`\
`s = "banana"`\
Output: `True`
```
bana|n|a
bana|b|a
only 1 character difference
```
* Input2:\
`li = ["orange","apple","banana"]`\
`s = "banana"`\
Output: `False`
```
banana
banana
0 character difference
```

* Input3:\
`li = ["orange","apple","banbba"]`\
`s = "banana"`\
Output: `False`
```
ban|an|a
ban|bb|a
2 character difference
```

* Input4:\
`li = ["orange","apple","banana"]`\
`s = "strawberry"`\
Output: `False`
```
not found in the list
```

```python
def compare(i,s,c=0):
    if len(i) == len(s): # if length of item in the list is equals to string 's' then proceed otherwise check for next item
        for j in range(len(i)):
            if i[j] == s[j]:
                c += 1 # counting the matching character
    if len(s)-c == 1: # if character difference is only 1 return true otherwise false
        return True
    else:
        return False

def comp(x,s):
    for i in x: # getting each item from list for comparing
        if compare(i,s):
            print("True")
            break
    else:
        print("False")


#client code
li = ["orange","apple","banaba"]
s = "banana"
comp(li,s)
```
## I hope you liked the code :smiley:

