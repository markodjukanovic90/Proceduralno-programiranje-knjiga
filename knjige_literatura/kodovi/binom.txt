def initialization(n, k):
  	    Binom = [[-1] * (k+1)  for _ in range(n+1)] 
  	    return Binom
  	    

def binom_memoization(i, j, Binom): 

        if Binom[i][j] != -1:
           return Binom[i][j] 
        if j == 0: 
           Binom[i][j] = 1
           return 1 
        if i < j: 
           Binom[i][j] = 0 
           return 0
        Binom[i][j] = binom_memoization(i-1, j-1, Binom) + binom_memoization(i-1, j, Binom) 
        return Binom[i][j]

#poziv metode:
n = 10
k = 4
Binom  = initialization(n, k) 
s = binom_memoization(n, k, Binom) 
print("Vrijednost bin. koeficijenta ", s)
