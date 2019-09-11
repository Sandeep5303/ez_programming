## Print the pattern for nth term
For example:
* Input1: `n=4`\
Output:
> Without spaces between every element
```
   #
  ##
 ###
####
```
* Input2: `n=6`\
Output:
> With spaces between every element
```
          #
        # #
      # # #
    # # # #
  # # # # #
# # # # # #
```
### Without spaces code:
```python
def pattern(n):
    c = n - 1 # first row always contains n-1 spaces
    for i in range(1,n+1):
        print(c*" " + i*"#")
        c -= 1 # decrementing space by 1 for next row
# client code
n = 4
pattern(n)
```
### With spaces code:
```python
def pattern(n):
    c = (n - 1)*2 # first row always contains (n-1)*2 spaces
    for i in range(1,n+1):
        print(c*" " + i*"# ")
        c -= 2 # decrementing space by 2 for next row
# client code
n = 6
pattern(n)
```

## I hope you liked the code :smiley:
