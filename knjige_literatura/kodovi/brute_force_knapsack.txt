best_fitness: float = 0.0

#instance example:
N = 4
w = [2, 5, 10, 5]
p = [20, 30, 50, 10]
C = 16
# helper function
def objective(solution):
    
    if len(solution) == 0: 
        return float('-inf')
    fitness: float = 0.0
    weight: float = 0.0
    
    for i in solution: 
        fitness += p[i]
        weight += w[i]
        
    if weight > C:
        return float('-inf')
    else:
        return fitness
    
# brute force recursion
def knapsack_brute_force(solution): 
    global best_fitness
    
    if objective(solution) > best_fitness:
        best_fitness = objective(solution) 

    for i in range(N):
        if  len(solution) >= 1: 
            if i > max(solution) : # symmetry breaking 
                print(solution + [i])
                knapsack_brute_force(solution + [i]) 
        else:
            knapsack_brute_force(solution + [i]) 

knapsack_brute_force([])
print(best_fitness)
