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
## 1399C. Boats Competition

```python
m=int(input())

for i in range(m):
    n=int(input())
    w=list(map(int,input().split()))
    
    max_team =0
    
    for j in range(2,2*n+1):
        l=0
        r=n-1
        curr=0
        while l<=r:
            total =w[l]+w[r]
            if total ==s:
                curr+=1
                l+=1
                r+=1
            elif total<s:
                left+=1
            else:
                right-=1
        max_team=max(max_team,curr)
        
    print(max_team)
```
