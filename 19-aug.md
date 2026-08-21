## 1006C - Three Parts of the Array ##
```python
n=int(input())
arr=list(map(int,input().split()))

sum1=0
sum2=0
max_sum=0

l=0
r=n-1

while l<=r:
    
    if sum1>sum2:
        sum2+=arr[r]
        r-=1
    else:
        sum1+=arr[l]
        l+=1
        
    if sum1 == sum2 :
        max_sum = max(max_sum,sum2)
    
print(max_sum)
```
