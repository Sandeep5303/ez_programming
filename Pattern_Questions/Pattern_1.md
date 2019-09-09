## From the values given in a list print this pattern
For example
* Input1: `l = [-2, 2, 3, 5, -4]`
```
    * * *
        * * *
        * * * *
        * * * * * *
* * * * *
```
* Input2: `l = [-1, 2, -3, 2, 3]`
```
      * *
        * * *
  * * * *
        * * * 
        * * * *
```
> This is question is based on numberline, the difference is that only we have to consider either 0 or above 0 value
> as origin, since index always start from 0 and not from -ve number. In above example -2 is the first element
> we cant print * from -2 to 0 for this the below code will help us out. It is best to solve pattern programs by
> making matrix and giving index values from 0 to n

### The above program can be done in many ways, from list also but here I am using arrays to implement this so that can try this code in C or C++ by just changing few lines of code

```python
l = [-2, 2, 3, 5, -4]
s = sorted(l) #1 sorting the list to get smallest -ve value and largest +ve value, this will help us to find number of columns needed
c = 0 #2 this will count the value for mid from where we can start adding * , in above example mid is 4, from 4 we are either decrementing or incrementing
f = len(l) #3 number of rows

if s[0] < 0: #4 After sorting, if first value is -ve then we can count the the number of columns by adding smallest -ve value(making it +ve first) and largest +ve value
    # of sorted list and adding 1 to it because in above example we can conclude that the index start from 0 to 8 that means 9 elements so adding 1 will make it 9
    k = s[0]*(-1) + s[len(s)-1] + 1 # -4*(-1) + 4 + 1 = 9(number of columns)
    for i in range(s[0], 0, 1):#5 In this we are finding how much steps the smallest -ve value takes to go to 0,from above example -4 will take 4 steps to go to 0
        # [-4 to -3], [-3 to -2], [-2 to -1], [-1 to 0]
        c += 1 # refer comment no.2 to know what c really does
else: #6 if first element of sorted list is +ve then we can simple start index from 0, for eg if element is 2 we can print * from 0 to 2, so no of columns reduced to
    # to only largest +ve value + 1
    k = s[len(s)-1] + 1 # try this on your own when list contains only +ve integer and calculate k

a = [[None for _ in range(k)] for _ in range(f)] #7 This will create a 2D array of k columns and f rows each containing None value
mid = c #8 assigning value of c to mid because now c will be used as a temp variable to assign 4 to mid each time loop overs
j = 0 #9 j will refer to rows of the array, here j is 0 because we will start adding * from 0th row

for i in l: #10 accessing each element from list l
    if i < 0: #11 if value is negative
        while mid >= c+i: 
            a[j][mid] = "*" #12 we will assign * to jth row and midth column, here j is 0 and mid is 4
            mid -= 1 #13 decrementing mid by 1 as we are going left of mid
    else: #14 if value is positive
        while mid <= c+i: 
            a[j][mid] = "*" #15 we will assign * to jth row and midth column, here j is 0 and mid is 4
            mid += 1 #16 incrementing mid by 1 as we are going right of mid
    j += 1 #17 incrementing j to 1 as we have finished adding * to Oth row, this will keep incrementing until all values in list l are traversed
    mid = c #18 assiging value of c to mid again for next row insertion refer to comment no 8 for more info

# Below code is for two purposes 1- to print all the values in array 2- to replace "None" by "_"(space)
for i in range(f):
    for j in range(k):
        if a[i][j] is None:
            a[i][j] = " "
        print(a[i][j],end=" ")
    print("")
```

## I hope you liked the code!!:smiley:
