#  Day54 - circular prime - Python
---

### 1.Import itertools
```
from itertools import permutations
```

### 2. decimal check
- Create a function to determine prime numbers
```
def is_prime(nums) :
  if nums < 2:
        return False
  for i in range(2, int(nums ** 0.5) + 1):
        if nums % i == 0:
            return False
  return True
```

### 3. Find repeating decimals
- Create a function to determine repeating decimals. The function is for each number from 2 to n−1:
Use the is_prime function to check if a number is prime.
If the number is prime, convert the number to a string to generate all permutations of the digits.
Checks whether all permutations are prime. If at least one is not a prime number, it is not a repeating prime number.
If all permutations are prime, add the numbers to the set of recurring primes.
Finally, it returns a set of repeating decimals.
```
def solution(n):
    cir_primes = set()
    for num in range(2, n):
        if is_prime(num):
            str_num = str(num)
            circular = True
            for perm in permutations(str_num):
                if not is_prime(int("".join(perm))):
                    circular = False
                    break
            if circular:
                cir_primes.add(num)
    return cir_primes
```

### 4.Print result
```
n = 1000000
result = len(solution(n))
print(result)
 
```




#  Day53 - Prime Factorization - Python
---

### 1.Import iter
```
from itertools import permutations
```

### 2. inputting an integer, factorize the prime number.
- Create a function to factorize prime numbers
```
def solution(n):
    nums = []
    while n > 1:
      for i in range(2, n+1):
         if n % i == 0:
          nums.append(i)
          n //= i
          break
    return nums
```

### 3. Print result
```
n = 12
result = solution(n)
print(result)
 
```





#  Day23 - Calculate the total number of pages needed - Python
---

### Get input
- Enter the total number of cases ('m'). Enter the number of posts ('n') to display on one page.
```
m = int(input("총 건수를 입력하시오:"))
n = int(input("한 페이지에 보여줄 게시물 수를 입력하시오:"))
```

### 2. Calculate total number of pages and print
- Determine the number of pages based on the remainder of m divided by n

```
if n >= 1 :
  if m % n == 0 :
    print(m//n)
  else :
    print((m//n)+1)
else :
  print("입력오류")
```
