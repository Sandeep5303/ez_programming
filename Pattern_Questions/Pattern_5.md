## Print Diamond pattern for nth term
For example
* Input1: `n=4`\
Output:
```
      *
     * *
    * * *
   * * * *
    * * *
     * *
      *
``` 
* Input2: `n=3`\
Output:
```
  * 
 * * 
* * * 
 * * 
  * 
``` 
**Code:**
```python
def diamond(n, temp, space, space2):
    for i in range(1,(2*n-1)+1):
        if i <= n:
            print(space*" ",end="")
            for j in range(0,i):
                print("*",end=" ")
            space -= 1
        else:
            print(space2*" ", end="")
            for j in range(temp-1,0,-1):
                print("*",end=" ")
            temp -= 1
            space2 += 1
        print()

#client code
n = 3
temp = n
space = n-1
space2 = 1
diamond(n,temp,space,space2)
```
## I hope you liked the code :smiley:
