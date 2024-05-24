 

"""
zadatak 2
#Neka je dat papir dimenzija A x B. Potrebno je isjeći papir na kvadrate bilo kojih 
#dimenzija. Napisati program koji pronalazi najmanji broj kvadrata koji mogu biti 
#izrezani od papira datih dimenzija. 
#Ulaz: 13 x 29 
#Izlaz: 9 
#2 (kvadrata veličine 13x13) + 4 (kvadrata veličine 3x3) + 3 (kvadrata veličine 1x1) 

"""
def nadji_najmanje(m,n):
    
    if m == n:
        return 1
    if m == 1 or n == 1:
        return max(m,n)
    if m == 0 or n == 0:
        return 0
    if m < n:
        k = n//m
        return k + nadji_najmanje(m,n-k*m)
    if m > n:
        k = m//n
        return k + nadji_najmanje(n,m-k*n)

if __name__ == '__main__':
    a = int(input("A = "))
    b = int(input("B = "))
    print(nadji_najmanje(a,b))
