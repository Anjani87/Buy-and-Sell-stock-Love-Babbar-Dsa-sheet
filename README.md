class Solution:
    #Function to find the days of buying and selling stock for max profit.
	def stockBuySell(self, A, n):
		#code here
		ans=[]
		i=0
		while i<n:
		    while i<n-1 and A[i+1]<=A[i]: #LOCAL MINIMA or BUY STOCK
		        i+=1
		    if i==n-1:
		        break
		    ans.append([i,-1])
		    i+=1
		    while i<n-1 and A[i+1]>=A[i]:  #LOCAL MAXIMA FOR SELL OF STOCK
		        i+=1
		    ans[len(ans)-1][1]=i
		    i+=1
        return ans
