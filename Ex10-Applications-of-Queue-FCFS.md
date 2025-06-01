# Ex10 Applications of Queue – FCFS
## DATE:
## AIM:
To write a C function to calculate the turnaround time of each process given their burst time and waiting time in First Come first Serve scheduling algorithm.
## Algorithm
1. Start with process, burst time, and waiting time arrays.
2. Loop through each process from i = 0 to n-1.
3. Compute tat[i] = burst_time[i] + wait_time[i].
4. End the algorithm

## Program:
```
Program to find and display the priority of the operator in the given Postfix expression
Developed by: S Mohamed Ahsan
RegisterNumber:  212223240089

int turnaroundtime( int proc[], int n,int burst_time[], int wait_time[], int tat[])
{
    int i;
    for ( i = 0; i < n ; i++)
    {
        tat[i] = burst_time[i] + wait_time[i];
    }
    return 0;
}
```

## Output:
![Screenshot 2025-04-29 211516](https://github.com/user-attachments/assets/03228fe5-d442-423a-a70f-7ddf84c2d4ff)




## Result:
Thus, the C function to calculate the turnaround time of each process given their burst time and waiting time in First Come first Serve scheduling algorithm is implemented successfully.
