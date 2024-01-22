from math import sqrt, pow

def FourSquareSum(sol):
 	      sum = 0
 	      for s in sol:
 	         sum += pow(s, 2)
 	      return int(sum)
 
def FourSumSquares(sol, n):
          if len(sol) == 4:
             if FourSquareSum(sol) == n:
                 print(sol)
          else:
             for i in range(1, int(sqrt(n))+1):
                 solI = sol + [i]
                 sum_sol_i = FourSquareSum(solI)
                 if sum_sol_i <= n-(4- len(solI)): # else backtrack  
                    FourSumSquares(solI, n) 
                    
FourSumSquares([], 20)
