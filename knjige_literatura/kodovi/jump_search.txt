def linear_search(arr, x, n):
	if n >= len(arr):
	    return -1
	
	if arr[n] == x:
	    return n
	
	return linear_search(arr, x, n+1)

 

def jump_search(niz, x, jump, k):
    
    if k * jump >= len(niz): #empty array
        return -1
        
    if k * jump < len(niz) and (k+1) * jump >= len(niz): 
        pos = linear_search(niz[k*jump :], x, 0)
        return pos + k*jump
    #rekurzivni korak: oba kraja intervala su elementi niza: 
    if niz[ k * jump ] <= x and x <= niz[ (k+1) * jump ]:
        pos = linear_search(niz[k*jump: ((k+1)*jump + 1)], x, 0)
        print("pos", pos, niz[k*jump: ((k+1)*jump + 1)])
        return pos + k*jump
    else:
        return jump_search(niz, x, jump, k+1) #move into the next interval

#instanca:
niz = [2, 10, 21, 33, 38, 41, 45, 52, 57, 70, 75]
jump_step = 3
x= 57
# poziv metoda:
pos = jump_search(niz, 57, jump_step, 0)
print(pos)
