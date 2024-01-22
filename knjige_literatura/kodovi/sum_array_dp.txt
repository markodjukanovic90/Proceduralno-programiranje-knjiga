def sum_array(niz, sum):
   	      #tabulation:
   	      DP = [[None] * (sum +1) for _ in range(len(niz) + 1) ]
   	      for i in range(len(niz)+1):
   	          DP[i][0] = True
   	      for j in range(1, sum+1):
   	          DP[0][j] = False
   	          
   	      for i in range(1, len(niz)+1):   
   	          for j in range(1, sum+1):
   	              if j >= niz[i-1]:
   	                 DP[i][j] = (DP[i-1][j-niz[i-1]] or DP[i-1][j])
   	              else:
   	                 DP[i][j] = DP[i-1][j]
   	      return DP[len(niz)][sum]

def init(niz, sum):
    global DP
    DP = [[-1] * (sum +1) for _ in range(len(niz) + 1) ]
    
    
def sum_array_top_down(niz, sum, i, j, DP = [ ]):
    
    if DP[i][j] != -1:
       return DP[i][j]
       
    if j == 0:
        DP[i][0] = True
        return True 
    if i == 0: 
       DP[0][j] == False
       return False
    #recursion: 
    if j >= niz[i-1]:
        DP[i][j] = sum_array_top_down(niz, sum, i-1, j, DP ) or   sum_array_top_down(niz, sum, i, j-niz[i-1], DP)
        return DP[i][j]
    else:
        DP[i][j] = sum_array_top_down(niz, sum, i-1, j, DP )
        return DP[i][j]

#instanca:
niz = [3, 34, 4, 12 ]
suma = 9
postoji = sum_array(niz, suma)
print("Postoji podniz sa sumom" if postoji else  
   	        "Ne postoji podniz sa sumom")

print("Top-down DP based approach ==> ")
DP = None
init(niz, suma)
postiji = sum_array_top_down(niz, suma, len(niz), suma, DP)
print("Postoji podniz sa sumom" if postoji else  
   	        "Ne postoji podniz sa sumom")

