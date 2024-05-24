def binary_search(arr, x):
	   
	    if len(arr) == 0:
	       return False 
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
	         
arr = [2, 8, 10, 12, 15]
x = 8
pos = binary_search(arr, x)
print(pos)
