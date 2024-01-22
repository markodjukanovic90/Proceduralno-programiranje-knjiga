	M = [ ] # matrica sa svim -1
	def init(n):
		for i in range(n):
			row = [ ]
			for j in range(n):
				row.append(-1)
				M.append(row)
		
		M[0][0] = A[0][0] #bazni slučaj
	
	def rec(i, j):
		if i == 0:
			return M[0][0]
		if M[i][j] != -1: #Podproblem vec izračunat
			return M[i][j]
		
		best = rec(i-1, j)
		if j > 0:
			best = max(best, rec(i-1, j-1))
		M[i][j] = best + A[i, j]
		return M[i][j]
