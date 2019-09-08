## Find and print all the sub-unsorted arrays
For example
* Input1:
`l = [1, 2, 4, 3, 1, 5]`\
output: `4 3 1`

* Input2:
` = [1, 2, 4, 3, 1, 5, 0]`\
output: `4 3 1`\
`5 0`

```python
def num_sub_array(x):
    s = []  # for storing sub-unsorted array
    c = 0  # flag variable
    for i in range(len(x)):
        if c == 0:
            if x[i] > x[i + 1]:  # 4 is found to be greater than 3 when i == 2
                s.append(x[i])  # adding 4 to s
                c = 1
                continue  # going to check loop again and skipping all the codes below
        elif len(s) != 0:
            if x[i] < s[0]:  # checking all next elements which are less than the number in s[0] i.e 4
                s.append(x[i])  # add them to s one by one
            else:
                print(*s)  # printing all the elements in s because 5 is found to be greater than 4 when i = 5
                s.clear()  # deleting all elements in s and making it ready for new sub-unsorted array
                if i != len(x) - 1 and x[i] > x[i + 1]:  # checking if we are at last element and if we are not at last element then checking whether it is greater than the next element
                    s.append(x[i])
        if i == len(x) - 2 and c == 0:  # if we are at the second last element and havent found any sub array yet then it is obvious that the array is sorted already
            print("No Unsorted Array Found")
            break
        elif i == len(x) - 1 and c == 1:  # this will help us to print more than one sub array
            print(*s)
# repeat the algo again for all values of i

# client code
lista = [1, 2, 4, 3, 1, 5]
num_sub_array(lista)
```
## I hope you liked the code!!:smiley:
