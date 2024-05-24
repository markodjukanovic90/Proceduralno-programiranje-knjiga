from math import sqrt, pow

def conflict(queenPos1, queenPos2):
    
    if queenPos1[1] == queenPos2[1]:
        return False
    # dialgonal conflict:
    
    
    
    
def valid(sol, N):
    
    for (i, q1) in enumerate(sol):
        for (j, q2) in enumerate(sol):
            if conflict( (i, q1), (j, q2)): #pairs (q_1, q_2)
               
    
    

def NQueens(niz, N):
       if len(niz) == N: # kompletno rješenje
               return niz
       else:
              for i in range(N):
                  niz = niz + [i]
                  if valid(niz): #backtrack ako nije 
                     NQueens(niz + [i])

N = 8
sol = NQueens([], N)       
if sol != None:
   print("Rješenje je: ", sol)
else:
   print("Nema rješenja") #npr. za N=3
