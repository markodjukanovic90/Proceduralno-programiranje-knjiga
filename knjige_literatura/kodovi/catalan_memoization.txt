def initialization(n):
	   Cat = [ -1   for _ in range(n+1)  ] 
	   return Cat 
	
def c(i, Cat): 
	
	if Cat[i] != -1:
	    return Cat[i]
	if i == 0: 
	   Cat[i] = 1
	   return 1 
     
    catalan_n = 0
    for k in range(i): 
        catalan_n += catalan_memoization(k, Cat) *
         catalan_memoization(i-k-1, Cat)
    
    Cat[i] = catalan_n
    return Cat[i]
    
	   
#poziv metode:
n = 10
Cat = initialization(n) 
	
cat_n = catalan_n(n, Cat) 
print(cat_n)
