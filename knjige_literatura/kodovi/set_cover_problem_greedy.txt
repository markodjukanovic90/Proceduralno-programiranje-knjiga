def g(X_S, C):
    
    return len((X.difference(X_S)).intersection(C))
    
def cover_X():
    
    X_S = set(())
    S = [] # solution
    
    while(X_S != X):
         C_star = None
         g_best = 0
         i_star = -1

         for i in range(len(F)):# iteration best-next
             if i  not  in S: 
                 g_i = g(X_S, F[i])
                 if g_best < g_i:
                     g_best = g_i
                     i_star = i
                     
         X_S = X_S.union((F[i_star])) #update cover
         print(X_S)
         S.append(i_star)
    return  S            
         
#instanca: 
X = {1, 2, 3, 4, 5}
F = [{1, 2, 3}, {1, 4}, {2, 4, 5}, {2, 3}, {4, 5}, {1, 5}]
sol = []
C = 50
sol = cover_X()
print(sol)

