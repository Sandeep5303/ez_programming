## Print all prime numbers between a and b
* Input1: `a=1,b=10`
Ouput: `2 3 5 7`
* Input2: `a=1,b=12`
Ouput: `2 3 5 7 11`
* Input1: `a=5,b=20`
Ouput: `7 11 13 17 19 `
```python
a,b = 1,10
for i in range(a,b):
    if i == a: # this statement will skip the first value because we need prime numbers between 'a' and 'b' so we
        # cant include 'a' whether it is prime or not
        continue
    else:
        for j in range(2, int(i ** .5) + 1):
            if i % j == 0: # if number is divisble by any of the number ranging from 2 to its square root, then it is
                # not a prime number 
                break
        else:
            print(i,end=" ") # print prime number if found
```
***or this part***
```
    if i == a: # this statement will skip the first value because we need prime numbers between 'a' and 'b' so we
        # cant include 'a' whether it is prime or not
        continue
```
***can be skipped by just adding +1 to a, so the code becomes***
```python
a,b = 1,10
for i in range(a+1,b):
    for j in range(2, int(i ** .5) + 1):
        if i % j == 0: # if number is divisble by any of the number ranging from 2 to its square root, then it is
            # not a prime number
            break
    else:
        print(i,end=" ") # print prime number if found
```
## I hope you liked the code :smiley:
