# Ex9 Applications of Queue - SJF
## DATE:
## AIM:
To incorporate the code to calculate the Total Waiting Time and Average Waiting Time in Shortest Job First scheduling algorithm.
## Algorithm
1. Start and read number of processes n and their burst times in bt[]; assign process IDs in p[].
2. Sort bt[] and p[] using selection sort based on burst time.
3. Compute waiting time wt[] by summing previous burst times.
4. Calculate turnaround time tat[] = bt[] + wt[] for each process.
5. Print average waiting time and turnaround time, then end.

## Program:
```
Program to find the Total Waiting Time and Average Waiting Time in Shortest Job First scheduling algorithm.
Developed by: S Mohamed Ahsan
RegisterNumber:  212223240089

#include<stdio.h>

int main() {
    int bt[20], p[20], wt[20], tat[20], i, j, n, total = 0, pos, temp;
    float avg_wt, avg_tat;
    
    scanf("%d", &n);
    
    for(i = 0; i < n; i++) {
        scanf("%d", &bt[i]);
        p[i] = i + 1;
    }
    
    for(i = 0; i < n; i++) {
        pos = i;
        for(j = i + 1; j < n; j++) {
            if(bt[j] < bt[pos])
                pos = j;
        }
        temp = bt[i];
        bt[i] = bt[pos];
        bt[pos] = temp;
        temp = p[i];
        p[i] = p[pos];
        p[pos] = temp;
    }
    
    wt[0] = 0;
    for(i = 1; i < n; i++) {
        wt[i] = 0;
        for(j = 0; j < i; j++)
            wt[i] += bt[j];
        total += wt[i];
    }
    
    avg_wt = (float)total / n;
    total = 0;
    
    printf("Process\tBurstTime\tWaitingTime\tTurnaroundTime\n");
    for(i = 0; i < n; i++) {
        tat[i] = bt[i] + wt[i];
        total += tat[i];
        printf("p%d\t%d\t\t%d\t\t%d\n", p[i], bt[i], wt[i], tat[i]);
    }
    
    avg_tat = (float)total / n;
    printf("\nAverage Waiting Time = %f", avg_wt);
    printf("\nAverage Turnaround Time = %f\n", avg_tat);
    
    return 0;
}
```

## Output:
![Screenshot 2025-04-29 211207](https://github.com/user-attachments/assets/b3a59d70-532a-4e59-ad9a-f4df52ee2eb0)




## Result:
Thus, the code to calculate the Total Waiting Time and Average Waiting Time in Shortest Job First scheduling algorithm is implemented successfully.
