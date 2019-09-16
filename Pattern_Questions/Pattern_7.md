## Print Pascal triangle for nth row
For example
* Input1: `n = 4`\
Output:
```
    1
   1 1
  1 2 1
 1 3 3 1
 ```
* Input2: `n = 5`\
Output:
```
    1 
   1 1 
  1 2 1 
 1 3 3 1 
1 4 6 4 1 
 ```
### Please try to implement yourself before reading the logic and code
> There are many ways to solve this problem, but here i am using combination formula method

* Logic:
>>>
Main logic of the problem is to find the <sup>n</sup>C<sub>r</sub> (combination formula) value where
<sup>n</sup>C<sub>r</sub> = n!/(r!*(n-r)!)
Lets take an example for n = 3
The output must be
>>>
```
0th row-   1
1st row-  1 1
2nd row- 1 2 1
The above pattern can be represented by (nCr)
0th row-       1
             (0C0)
1st row-    1     1  
          (1C0) (1C1)
2nd row-  1    2    1
        (2C0)(2C1)(2C2)
so we need two for loops 'i' and 'j'
i for n
j for r
```
Note:
> The <sup>n</sup>C<sub>r</sub> values gives the corresponding number by `nCr = n!/(r!*(n-r)!)` formula, For example 2C0 = 1 and 2C1 = 2 etc.

**Code:**
```python
from math import factorial as f
n = 5
c = n-1
for i in range(0,n):
    print(c*" ",end="")
    for j in range(0,i+1):
            res = f(i)//(f(j)*f(i-j))
            print(res,end=" ")
    c -= 1
    print()
```
## I hope you liked the code :smiley:
