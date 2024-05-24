def stick_cut(d, price):
   
     DP = [-1] * (d)  #init
     DP[0] = 0
     DP[1] = price[0]
     
     for i in range(2, d):
         
         for k in range(1, i+1):
             if DP[i] < DP[i-k] + price[k-1]: 
                DP[i] =  DP[i-k] + price[k-1]
     print(DP)
     return DP[d-1]     
         
#instanca
d = 4
price = [1, 5, 8, 9, 10, 17, 17, 20] 
#poziv:
max_profit = stick_cut(d, price) 
print(max_profit)

