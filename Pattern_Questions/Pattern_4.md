## Print the pattern for nth
For example:
* Input1: `n=5`\
Output:
```
    *
   ***
  *****
 *******
*********
```
* Input2: `n=3`\
Output:
```
  *
 ***
*****
```
```python
n = 3 
c = n-1
for i in range(1,n+1):
    print(c*" " + "*"*(2*i-1),end="") # here 2*i-1 shows the relation between row number and the number of '*' to be printed for that row
    print()
    c -= 1
```
## I hope you liked the code :smiley:
