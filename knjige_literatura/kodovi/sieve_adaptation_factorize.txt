def sieve_adaptation(n):
   
        sieve_fact = [0] * (n+1)
        sieve_fact[0] = sieve_fact[1] = 0
       
        p = 2
        while p <= n:
            
            if sieve_fact[p] == 0:
       
                index = 2 * p
                while index <= n:
                    sieve_fact[index] = p
                    index += p
            p = p + 1
 	
        return sieve_fact
 	
def factorization(n):
    
    factorize_min_p = sieve_adaptation(n)
    print(factorize_min_p)
    
    F = []
    while True: 
        i = factorize_min_p[n]
        if i == 0:
            F.append(n) 
            break
        else:
            n = n // i
            F.append(i)
    
    return F  
   
#ulaz: 
n = 120
F = factorization(n)
print("Lista faktora je: ", F)
