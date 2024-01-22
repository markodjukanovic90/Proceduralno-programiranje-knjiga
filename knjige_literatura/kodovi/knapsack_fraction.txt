def fraction(i):
    return P[i]/ W[i]
    
def fraction_knapsack():
    
    products = [i for i in range(len(W))] #lsit of prods
    products.sort(key = fraction, reverse=True)
    print(products)
    C_curr = C
    sol = []
    parts = []
    
    for i in products:
        
        part = min(C_curr / W[i], 1)
        
        print(sol, " ", parts)
        if part >= 1.0:
           part = 1
        
        if part > 0:
            sol.append(i)
            parts.append(part)
            C_curr -= part * W[i]
        else:
            return sol, parts
    return sol, parts
#instanca: 
W = [10, 20, 30]
P = [60, 100, 120]
C = 50
sol, parts = fraction_knapsack()
print(sol, " parts: ", parts)

