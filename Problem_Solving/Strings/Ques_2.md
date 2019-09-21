## Given a string S, print the size of the largest palindrome of all the substrings of S.

For example

Input1: `S = 'ababa'`
```
Substrings of S and largest palindrome size:
a = 1 (a)
ab = 1 (a or b)
aba = 3 (aba)
abab = 3 (aba or bab)
ababa = 5 (ababa)

Output:
1 1 3 3 5
```

Input2: `S = 'aabcbda'`
```
Substrings of S and largest palindrome size:
a = 1 (a)
aa = 2 (aa)
aab = 2 (aa)
aabc = 2 (aa)
aabcb = 3 (bcb)
aabcbd = 3 (bcb)
aabcbda = 3(bcb)

Output:
1 2 2 2 3 3 3
```

**Note:**
```
While going through the code you will encounter a phrase "possible combination of substrings of substring"
The explation is written below:
Lets take an example
String S = 'ababa'
its substrings are
1. a
2. ab
3. aba
4. abab
5. ababa

lets take the third substring i.e 'aba'
now all the possible combination substrings of 'aba' are:
a
ab
aba
b
ba
```

**Code:**
```python
def check(k):
    max = 0
    n = len(k)
    for i in range(n):  # creating all the possible combination of substrings of substring, for eg: - if substring is ab
        # then its all possible substrings are a,ab,b
        sub_str = ''
        for j in range(i + 1, n + 1):
            sub_str = k[i:j]
            rev = sub_str[::-1]
            if rev == sub_str and len(sub_str) > max:  # checking for largest palindrome inside substring
                max = len(sub_str)
    return max  # returning largest palindrome size found to k

def find_palin(s, n):
    l = []
    for i in range(0, n):
        sub_str = ''
        for j in range(0, i + 1):  # creating substrings of S
            sub_str = sub_str + s[j]
        rev = sub_str[::-1]  # reversing the substring
        if rev == sub_str:  # checking for palindrome
            l.append(len(sub_str))
        else:
            k = check(sub_str)  # if palindrome not found at first attempt then send to check function
            l.append(k)
    print(*l)
    
# client code
s = 'ababa'
n = len(s)
find_palin(s, n)
```

### I hope you liked the code :smiley:
