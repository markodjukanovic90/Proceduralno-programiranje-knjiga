from math import ceil
def lucky_number(n):
 
    for i in range(1, n): #iteracije
        if i+1 > ceil(n/i):
           return True  
        if ceil(n/i)  % (i+1) == 0:
           return False
    return True  
    
print(lucky_number(7))
