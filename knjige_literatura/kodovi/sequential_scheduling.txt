#instanca:
num_jobs = 5
Jobs = [i for i in range(num_jobs)]
Deadline = [2, 1, 2, 1, 3]
Profit = [100, 19, 27, 25, 15]


def ProfitSort(i):
    return Profit[i]
    
# možemo li dodati i-ti proizvod ili ne (-1) u I_s
def find_next_interval(I_s_covered, i):
    
    for index, covered in enumerate(I_s_covered):
        if index >= Deadline[i]:
            return -1
        if covered == False:
            return index
    return -1        
    
def sequnetial_scheduling():
    
    I_s_covered = [False] *  max(Deadline) 
    I_s = []
    #sortiranje jobs u odnosu na Profit (preprocessing):
    Jobs.sort(key=ProfitSort, reverse=True)
    #print(Jobs)
    for i in Jobs:
        
        interval = find_next_interval(I_s_covered, i)
        if interval >= 0: #nadjena (dopustiv) interval:
           I_s_covered[interval] = True #zauzet
           I_s.append(i)

    return I_s, sum([ Profit[I_s[i]]  for i in range(len(I_s)) ])

        
I_s, profit = sequnetial_scheduling()
print(I_s, " profit: ", profit)
