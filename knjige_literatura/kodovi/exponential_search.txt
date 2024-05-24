def binary_search(arr, x):
	   
	    if len(arr) == 0:
	       return -1 
	    if len(arr) == 1:
	       if arr[0] == x:
	          return 0
	       else:
	          return -1

	    mid = len(arr) // 2
	    if arr[mid] == x:
	       return mid
	    elif arr[mid] < x:
	         return binary_search(arr[mid+1:], x)
	    else: 
	         return binary_search(arr[:mid], x)


def exponential_search(niz, x, l):
    
    if len(niz) <= 1:
        if x in niz:
           return  l + int(x in niz)
        else:
           return -1 
    
    if l == 0:
       pos = 2
    else:
       pos = l * 2
       
    if pos >= len(niz):
        ind_found = binary_search(niz[l:], x)
        #print(ind_found)
        if ind_found == -1: # ako x ne postoji u sufiksu
           return -1
        else:
           return l + binary_search(niz[l:], x)
    else:
        if niz[l] <= x and x <= niz[pos] :
           return l + binary_search(niz[l: pos+1], x)
        else:
            return exponential_search(niz, x, pos)
# instanca:
niz = [2, 10, 22, 38, 44, 51, 100, 220, 550, 880]
x = 10
# poziv funkcije: 
print(exponential_search(niz, x, 0))

