
def fib(n, cache={}):#memoizacija
	if n in cache:
		return cache[n]
	if n == 0:
		return 0
	elif n == 1:
		return 1
	else:
		res = fib(n-1) + fib(n-2)
		cache[n] = res
		return res

def fibTab(n):#tabuliranje
	if n == 0:
		return 0
	elif n == 1:
		return 1
	else:
		tab = [0] * (n + 1) #init
		tab[0] = 0
		tab[1] = 1
		for i in range(2, n+1):
			tab[i] = tab[i-1] + tab[i-2]
		return tab[n]
