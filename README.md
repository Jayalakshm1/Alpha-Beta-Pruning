Lab Experiment 4: AlphaBeta Pruning

Write a python program to implement alpha beta pruning.

```Program:

MAX, MIN = 1000, -1000
def minimax(depth, nodeIndex, maximizingPlayer,values, alpha, beta):
    if depth == 3:
        return values[nodeIndex]
    if maximizingPlayer:
        best = MIN
        for i in range(0, 2):  
            val = minimax(depth + 1, nodeIndex * 2 + i,False, values, alpha, beta)
            best = max(best, val)
            alpha = max(alpha, best)
            if beta <= alpha:
                break
        return best
    else:
        best = MAX
        for i in range(0, 2):
            val = minimax(depth + 1, nodeIndex * 2 + i,True, values, alpha, beta)
            best = min(best, val)
            beta = min(beta, best)
            if beta <= alpha:
                break
        return best
values = [3, 5, 6, 9, 1, 2, 0, -1] 
print("The optimal value is :", minimax(0, 0, True, values, MIN, MAX))
```
Output:

![Screenshot 2024-02-24 115328](https://github.com/Jayalakshm1/Alpha-Beta-Pruning/assets/130430542/07f84e6a-27f4-4387-9834-5c2aed202e41)

Result:

Thus,a python program to implement alpha beta pruning was executed successfully.
