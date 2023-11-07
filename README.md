# OS-EX.10-IMPLEMENTATION-OF-PAGE-REPLACEMENT-ALGORITHMS

(Follow template provided in CPU Scheduling algorithms for sub divisions)

AIM:

To write a C program to implement Page Replacement technique using FIFO

ALGORITHM:

Start the program.

Get the number of pages and their sequence from the user

Get the number of available page frames from the user.

In FIFO, on the basics of first in first out, replace the pages respectively, then find number of page faults occurred.

Compare all frames with incoming page� 6. If the incoming page is already available in page frame, set the match flag to indicate ‘no need of page replacement’.

If the incoming page is not available in all frames, then remove the page which is loaded into the memory long back and give space for new incoming page.

Increment the ‘number of Page faults counter

Print the number of page faults.

Stop the program.



PROGRAM:
```
#include<stdio.h>
int main()
{
    int i, j, n, a[50], frame[10], no, k, avail, count = 0;
    printf("\n ENTER THE NUMBER OF PAGES:\n");
    scanf("%d", &n);
    printf("\n ENTER THE PAGE NUMBER :\n");
    for(i = 1; i <= n; i++)
        scanf("%d", &a[i]);
    printf("\n ENTER THE NUMBER OF FRAMES :");
    scanf("%d", &no);
    for(i = 0; i < no; i++)
        frame[i] = -1;
    j = 0;
    printf("\tRef string\t Page Frames\n");
    for(i = 1; i <= n; i++){
        printf("%d\t\t\t", a[i]);
        avail = 0;
        for(k = 0; k < no; k++){
            if(frame[k] == a[i]){
                avail = 1;
                break;}
        }
        if (avail == 0){
            frame[j] = a[i];
            j = (j + 1) % no;
            count++;
            for(k = 0; k < no; k++){
                if(frame[k] == -1)
                    printf("-\t");
                else
                    printf("%d\t", frame[k]);}}
        printf("\n");}
    printf("\nPage Fault Is %d", count);
}
```

OUTPUT:

![image](https://github.com/Subhikshaa13/OS-EX.10-IMPLEMENTATION-OF-PAGE-REPLACEMENT-ALGORITHMS/assets/118787344/0d64477c-0693-4153-98c1-db1a04634ea1)


RESULT:

Thus the implementation of LRU page replacement is successfully executed.
