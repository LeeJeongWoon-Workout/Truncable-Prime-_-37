# Truncable-Prime-_-37

def get_prime(n):
    sieve=[True]*(n+1)
    for i in range(2,int(n**0.5)+1):
        if sieve[i]:
            for j in range(i+i,n+1,i):
                sieve[j]=False
    return [str(i) for i in range(2,(n+1)) if sieve[i]]

list_prime=get_prime(1000000)
list_solution=[]
for i in list_prime:
    l=len(i)
    t=0
    m=0
    for j in range(l+1):
        k=i[0:j]
        if k in list_prime:
            t+=1
    for j in range(l):
        k=i[j::]
        if k in list_prime:
            m+=1
    if t==l and m==l:
        list_solution.append(i)
    l=len(list_solution)-4
    if l==11:
        break
print(sum(list_solution)-17)
