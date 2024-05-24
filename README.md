#  Day54 - circular prime - Python
---

### 1.Import itertools
```
from itertools import combinations
```

### 2.Initialize count + Input list
- The input is provided in the form of a list like [1,2,3,4], But when entered, python does not recognize it as a list. Therefore, it requires additional processing to remove the brackets at the beginning and end using [1:-1], and then splitting the string by commas using split(",").
```
count = 0
num = list(map(int,input()[1:-1].split(",")))
```

### 3.Decimal discrimination
- According to the requirements, I use combinations(num, 3) to create combinations of 3 elements each, and evaluate each of these values using a for loop. Since the value i is in tuple form and we no longer need it, I reassign i to the sum of the tuple with i = sum(i). Then determine if the value of i is a prime number, and if it is, increment the count by 1.
```
for i in combinations(num,3):
    i = sum(i)
    c = True
    for k in range(2,int(i**0.5)+1):
        if i%k == 0:
            c = False
            break
    if c == True:
         count += 1
```

### 4.Print result
```
print(count)
```
