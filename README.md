# CSCK541
Liverpool Univ. SCSCK541
student name : LEE HOCHOLE

## PDF Code ,by lecture 

def floyd(distance):
  """
  A simple implementation of Floyd's algorithm
  """
  for intermediate, start_node,end_node\
  in itertools.product\
  (range(MAX_LENGTH),range(MAX_LENGTH), range(MAX_LENGTH)):

      ### Assume that if start_node and end_node are the same
      ### then the distance would be zero
      if start_node == end_node:
      distance[start_node][end_node] = 0
        continue
        
      ###return all possible paths and find the minimum
      distance[start_node][end_node] = min(distance[start_node][end_node],
          distance[start_node][intermediate] + distance[intermediate][end_node] )

  #Any value that have sys.maxsize has no path
  print (distance)
floyd(graph)

### CODE 1 using Hompage 

 
V = 4
INF = 99999 
def floydWarshall(graph):

    dist = list(map(lambda i: list(map(lambda j: j, i)), graph))
 
    for k in range(V):
 
        
        for i in range(V):
           
            for j in range(V):
                 
                dist[i][j] = min(dist[i][j],
                                 dist[i][k] + dist[k][j]
                                 )
    printSolution(dist)
 
 
def printSolution(dist):
    print("Following matrix shows the shortest distances\
 between every pair of vertices")
    for i in range(V):
        for j in range(V):
            if(dist[i][j] == INF):
                print("%7s" % ("INF"), end=" ")
            else:
                print("%7d\t" % (dist[i][j]), end=' ')
            if j == V-1:
                print()
 
 
#### Driver's code
if __name__ == "__main__":
    """
                8
           (1)------->(4)
            |         /|\
          7 |          |
            |          | 2
           \|/         |
           (2)------->(3)
                5           """
    graph = [[0, 7, INF, 8],
             [INF, 0, 5, INF],
             [INF, INF, 0,   2],
             [INF, INF, INF, 0]
             ]
    # Function call
    floydWarshall(graph)
#### This code is contributed by Mythri J L





## CODE 2 , by myself 


def floyd(w):
    D = w
    n = len(w)
    for k in range(n):
        for i in range(n):
            for j in range(n):
                D[i][j] = min(D[i][j], D[i][k] + D[k][j])
    return D

INF = 999
w = [[0, 7, INF, 8],
     [INF, 0, 5, INF],
     [INF, INF, 0, 2],
     [INF, INF, INF, 0]]

D = floyd(w)
for i in range(len(D)):
    print(D[i])
  
