## Given a positive integer number, check whether it is palindrome or not, if it is then print it otherwise add the
number with its reverse and perform this step until it becomes a palindrome and print the new palindrome found.

For example

Input1: `n = 121`\
Output: `121 is palindrome`

Input2: `n = 908`\
Output: `8888 is palindrome`

### Please try to implement yourself before reading the logic and code

* Logic:
```
Logic is to add the reverse of the number to the original number and recursively calling the function again if palindrome not found at
first attempt.
For example:
n = 908, rev = 809, new_num = n + rev = 1717...calling palindrome(1717) again
n = 1717, rev = 7171, new_num = n + rev = 8888, palindrome found
```
* Code:
```python
def palindrome(num):
    sum = 0
    temp = num

    # To reverse the number
    while num != 0:
        r = num % 10
        sum = sum*10 + r
        num = num // 10

    if sum == temp:
        print(temp, "is palindrome")
    else:
        a = temp + sum
        palindrome(a) # calling again with new added number

#client code
n = int(input())
palindrome(n)
```

## I hope you liked the code :smiley:
