# POLICY EVALUATION

## AIM
To develop a Python program to evaluate the given policy.

## PROBLEM STATEMENT
To find best policy from two policies which are defined by user using policy evaluation function. Where the mdp includes 16 states from 0-15, 0 is the starting state, assigning some 4 random state as holes and 15 is the goal state and then we need to calculate optimal state value function for each state such that we can reach goal using optimal policy using policy evaluation.
## POLICY EVALUATION FUNCTION
```
def policy_evaluation(pi, P, gamma=1.0, theta=1e-10):
    prev_V = np.zeros(len(P), dtype=np.float64)
    # Write your code here to evaluate the given policy
    while True:
      V=np.zeros(len(P))
      for s in range(len(P)):
        for prob,next_state,reward,done in P[s][pi(s)]:
           V[s]+=prob*(reward+gamma *prev_V[next_state]*(not done))
      if np.max(np.abs(prev_V-V))<theta:
        break
      prev_V=V.copy()
    return V
```
## OUTPUT:
### First policy:

![image](https://github.com/user-attachments/assets/fc9f4486-6d6c-48a6-b075-7ea4053718c1)
![image](https://github.com/user-attachments/assets/acd002ba-088b-42f0-956b-00e830dbe6b3)

### Second policy:
![Screenshot 2025-05-14 151609](https://github.com/user-attachments/assets/f36a0922-36c4-4395-9217-d92463fdcf4c)


![image](https://github.com/user-attachments/assets/92ddac3f-c022-49cf-92e4-ac0669026e63)

### First and Second compared them:
![image](https://github.com/user-attachments/assets/0b64f2ca-6e1f-423e-92c8-2540224b102e)



## RESULT:
Thus, The Python program to evaluate the given policy is successfully executed.
