# day-5-c..

# Patterns
1.hollow diamond pattern 
#include <stdio.h>

int main() {
    int n = 4, i, j;

  /* Upper half */
    for (i = 1; i <= n; i++) {
        for (j = 1; j <= n - i; j++)
            printf(" ");
        printf("*");
        if (i > 1) {
            for (j = 1; j <= 2 * i - 3; j++)
                printf(" ");
            printf("*");
        }
        printf("\n");
    }

  /* Lower half */
    for (i = n - 1; i >= 1; i--) {
        for (j = 1; j <= n - i; j++)
            printf(" ");
        printf("*");
        if (i > 1) {
            for (j = 1; j <= 2 * i - 3; j++)
                printf(" ");
            printf("*");
        }
        printf("\n");
    }
    return 0;
}
output:
  *
  * *
 *   *
*     *
 *   *
  * *
  * 

2.hourglass pattern 
#include <stdio.h>

int main() {
    int n = 4, i, j;

  * Upper half (7 5 3 1 stars) */
    for (i = 0; i < n; i++) {
        for (j = 0; j < i; j++)
            printf(" ");
        for (j = 0; j < 2 * (n - i) - 1; j++)
            printf("* ");
        printf("\n");
    }

    /* Lower half (3 5 7 stars) */
    for (i = n - 2; i >= 0; i--) {
        for (j = 0; j < i; j++)
            printf(" ");
        for (j = 0; j < 2 * (n - i) - 1; j++)
            printf("* ");
        printf("\n");
    }
    return 0;
}
output:

* * * * * * *
 * * * * *
  * * *
   *
  * * *
 * * * * *
* * * * * * *
3.pascal triangle 

#include <stdio.h>

int main() {
    int n = 5, i, j, num;

  for (i = 0; i < n; i++) {
        for (j = 0; j < n - i - 1; j++)
            printf("  ");
        num = 1;
        for (j = 0; j <= i; j++) {
            printf("%4d", num);
            num = num * (i - j) / (j + 1);
        }
        printf("\n");
    }
    return 0;
}
output:

           1
         1   1
       1   2   1
     1   3   3   1
   1   4   6   4   1
