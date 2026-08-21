## Question 1: 
Frog Jump Problem description A frog moves through indexed stones with given heights. It may jump one or two positions and pays the absolute height difference. 
Find minimum total energy.  
Input 
  format n followed by n heights.  
Output 
  format Print the minimum energy.
# code
```python
n=int(input())
heights = list(map(int,input().split()))

dp=[0]*(n)

dp[0]=heights[0]
dp[1]= abs(heights[0]-heights[1])

for i in range (2,n):
    one = dp[i-1]+abs(heights[i-1]-heights[i])
    two =dp[i-2]+abs(heights[i-2]-heights[i])
    
    dp[i]=min(one,two)
    
print(dp[n-1])

```
---
## Question 2: 
Frog Jump with K Distances Problem description The frog may jump from a stone to any of the next k stones. 
Each jump costs the absolute height difference. Minimize total energy.  
Input 
  format n k, then n heights.  
Output 
  format Print minimum energy.
# code
```python
```

  
