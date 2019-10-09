# TD1-informatique
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
Created on Fri Oct  4 20:19:19 2019

@author: Assia
"""

#problème1
def solve(n):
    s=0
    for k in range (n):
        if k%3==0 or k%5==0 : 
            s+=k
    return (s)



#problème2
def solve2(n):
    L=(1,2)
    t=L[0]+L[1]
    while t<=n :
        L=L+(t,)
        t=L[-1]+L[-2]
    s=0
    for i in (L):
        if i%2==0 :
            s+=i
    return s
    

#problème3
def testdeprimarite(n):
    if n==1 :
        return False
    N=int(n**(1/2))
    L=(n,)
    k=1
    while k<=N : 
        if n%k==0:
            L=L+(k,)
            k+=1
        else :
            k+=1
            
    if L==(n,1):
        return True
    
    else :
        return False
        
def diviseurs(n):
    if testdeprimarite(n)==True :
        return ((1,n),n)
    else:
        V=(1,n)
        for k in range (2,n+1):
            if n%k==0:
                if testdeprimarite(k)==True:
                    V=V+(k,)
        
        max=V[-1]
        return (V,max)

#problème4

def palindromique(nombre): #permet de savoir si un nombre est 'palindromique' ou non
    compteur = 0
    L = [str(c) for c in str(nombre)] #transforme le nombre en la liste de ses chiffres
    for i in range(len(L)//2):
        if L[i] == L[len(L)-i-1]:
            compteur += 1
    if compteur == len(L)//2: #si tous les nombres symétriquement répartis par rapport au centre du nombre sont égaux, le nombre est 'palindromique'
        return True
    else:
        return False
    
def biggestpalindrome(n):
    M=10**(n-1)
    a,b=M,M
    p=a*b
    for a in range(M,M*10):
        for b in range (M,M*10):
            x=a*b
            if palindromique(x)==True:
                if x>p:
                    p=x
    return (p,a,b)



#problème5


def divisible (x,n):
    s=0
    for k in range (1,n+1):
        if x%k==0 :
            s+=1
    if s==n:
        return True
    else : 
        return False

def smallestmultiple(n):
    i=n
    while divisible (i,n)==False :
        i+=1
    return i            
         
        
#problème6
def sommedescarré(n):
    s=0
    for k in range (n+1):
        s+=(k)**2
    return s

def sommeaucarré(n):
    s=0
    for k in range (n+1):
        s+=k
    return s**2

def problème6(n):
    return -sommedescarré(n)+sommeaucarré(n)

#problème7
def problème7(n):
    L=[]
    k=0
    while len(L)<n:
        if testdeprimarite(k)==True :
            L.append(k)
        k=k+1
    print(L[-1])



#problème9
def pythagore(n):
    for a in range (1,n+1):
        for b in range (1,n+1):
            c=n-a-b
            if a**2+b**2==c**2:
                return a*b*c
            

#problème10
def sumprimes(n):
    s=0
    for k in range (n+1):
        if testdeprimarite(k)==True:
            s+=k
    return s


#PROBLeme 16
def solve16(n):
    s= 0
    for chiffre in [int(c) for c in str(2**n)]: #transforme le nombre en la liste de ses chiffres
        s += chiffre
    return s





print('la solution du problème1 est')
print(solve(1000))
print('la solution du problème2 est')
print(solve2(4000000))
print('la solution du problème4 est')
print(biggestpalindrome(3))     
print('la solution du problème6 est')  
print(problème6(100))
print('la solution du problème7 est')  
print(problème7(10001))
print('je n arrive pas a faire le problème8')
print('la solution du problème9 est')  
print(pythagore(1000))
print('la solution du problème10 est') 
print(sumprimes(2000000))
print('la solution du problème16 est') 
print(solve16(1000))
print('la solution du problème3 est (très lente)')
print(diviseurs(600851475143))  
print('la solution du problème5 est(très lente)')  
print(smallestmultiple(20))  



