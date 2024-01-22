	    	def LCS(s1, s2):
	    	      
	    	      if len(s1)==0 or len(s2)==0:
	    	         return 0
	    	      
	    	      DP = [ [0]*(len(s2)+1) for _ in range(len(s1)+1)]
	    		  for i in range(1, len(s1)+1):
	    		      for j in range(1, len(s2)+1):
	    		          if s1[i] == s2[i]: 
	    		             DP[i][j] = DP[i-1][j-1] + 1:
	    		          else:
	    		             DP[i][j] = max(DP[i-1][j], DP[i][j-1])
	    		          
	    		  return DP[len(s1)][len(s2)]        
	    		           
	    	      
	    	#instanca:
	    	s1 = "abcdcdcdaa"
	    	s2 = "abbaabcccddd"
	    	lcs = LCS(s1, s2)
	    	print("Duzina LCS-a je: ", lcs)   
