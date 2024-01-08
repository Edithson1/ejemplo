class Solution:
  def minimumEffortPath(self, M) -> int:
    m,n = len(M), len(M[0])
    if bool(n) and bool(m):
      matris = [[float('inf')] * n for _ in range(m)]
      matris[0][0]= 0
      for i in range(m):
        for j in range(n):
          if i-1 >=0:
            matris[i][j]= min(matris[i][j], abs(M[i-1][j]-M[i][j]))
          if j-1 >=0:
            matris[i][j]= min(matris[i][j], abs(M[i][j-1]-M[i][j]))
      return matris[-1][-1]
    else: return 0
