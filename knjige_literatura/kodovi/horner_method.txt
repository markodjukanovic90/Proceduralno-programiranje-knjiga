	 	 def horner_metod(coef, n, x):
	 	    
	 	    if n == 0: 
	 	       return coef[0]
	 	    
	 	 	# inicijalizacija
	 	 	res = coef[n]  * x
 
	 	 	for i in range(1, n):
	 	 
	 	     	res = res + coef[i]
	 	     	if i < n-1:
	 	     		res *= x
	 	 
	 	 	return res
	 	 
	 	 # poziv funkcije
	 	 # Evaluacija:  x^3 - 3 x^2 + 2 x -1, x = 3
	 	 coef = [1, -3, 2, -1]
	 	 x = 3
	 	 n = len(coef)
	 	 print(horner_metod(coef, n, x))
