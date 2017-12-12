# Exercises

1)
	
```c
#include <stdio.h>

int main()
{
    int digit_seen[10] = {0};
    int digit, i;
    long n;

    printf("Enter a number: ");
    scanf("%ld", &n);
    while (n > 0) {
        digit = n % 10;
        digit_seen[digit] = 1;
        n /= 10;
    }

    for (i = 0; i < 10; i++)
        if (digit_seen[i])
            printf("%d ", i);
    putchar('\n');

    return 0;
}

```
2)  

```c
#include <stdio.h>

int main()
{
    int digit_seen[10] = {0};
    int digit, i;
    long n;

    printf("Enter a number: ");
    scanf("%ld", &n);
    while (n > 0) {
        digit = n % 10;
        digit_seen[digit]++;
        n /= 10;
    }

    printf("Digit:       ");
    for (i = 0; i < 10; i++)
        printf("%d", i);
    putchar('\n');

    printf("Occurrences: ");
    for (i = 0; i < 10; i++)
        printf("%d", digit_seen[i]);

    putchar('\n');

    return 0;
}
```
3)

```c
#include <stdio.h>

#define NUM_RATES ((int) (sizeof(value) / sizeof(value[0])))
#define INITIAL_BALANCE 100.00

int main(void)
{
    int i, j, base_rate, num_years, year;
    double value[5];

    printf("Enter interest rate: ");
    scanf("%d", &base_rate);
    printf("Enter number of years: ");
    scanf("%d", &num_years);
    printf("\nYears");

    for (i = 0; i < NUM_RATES; i++) {
        printf("%13d%%", base_rate + i);
        value[i] = INITIAL_BALANCE;
    }

    printf("\n");

    for (year = 1; year <= num_years; year++) {
        printf("%3d    ", year);
        for (i = 0; i < NUM_RATES; i++) {
            for (j = 0; j < 12; j++)
                value[i] += (base_rate + 1) / 100.0 * value[i];
            printf("%14.2f", value[i]);
        }
        printf("\n");
    }

    return 0;
}
```
4)

```c
#include <stdio.h>

int main(void)
{
    int i, j, total, min, max;
    int grades[5][5] = {0};

    for (i = 0; i < 5; i++) {
        printf("Enter grades for student %d: ", i + 1);
        scanf("%d %d %d %d %d", &grades[i][0], &grades[i][1], &grades[i][2], &grades[i][3], &grades[i][4]);
    }

    for (i = 0; i < 5; i++) {
        total = 0;
        for (j = 0; j < 5; j++)
            total+= grades[i][j];
        printf("Student: %d total: %d avg: %.2f\n", i + 1, total, total / 5.0f);
    }

    for (i = 0; i < 5; i++) {
        total = 0;
        min = 999;
        max = -1;
        for (j = 0; j < 5; j++) {
            total+= grades[j][i];
            if (grades[j][i] > max)
                max = grades[j][i];
            if (grades[j][i] < min)
                min = grades[j][i];
        }
        printf("Test: %d avg: %.2f min: %d max: %d\n", i + 1, total / 5.0f, min, max);
    }

    return 0;
}
```
5)

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define N 10
#define SIZEL ((int) (sizeof(letters) / (sizeof(letters[0])))

int main(void)
{
    char random_walk[N][N];
    int i, j, x, y, flag, move;
    const char letters[] = {'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I',
                            'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R',
                            'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'};

    srand((unsigned) time(NULL));
    /* srand(1231); */
    x = y = 0;

    for (i = 0; i < N; i++)
        for (j = 0; j < N; j++)
            random_walk[i][j] = '.';

    for (i = 0; i < 24; i++) {
        flag = 1;
        /* move = rand() % 4; */
        /* printf("%d\n",move); */
        /* break; */
        while (flag) {
            move = rand() % 4;
            if (move == 0) {
                if (x-1 >= 0 && random_walk[x-1][y] == '.') {
                    flag = 0;
                    x--;
                    random_walk[x][y] = letters[i];
                }
            } else if (move == 1) {
                if (x+1 <= 9 && random_walk[x+1][y] == '.') {
                    flag = 0;
                    x++;
                    random_walk[x][y] = letters[i];
                }
            } else if (move == 2) {
                if (y-1 >= 0 && random_walk[x][y-1] == '.') {
                    flag = 0;
                    y--;
                    random_walk[x][y] = letters[i];
                }
            } else if (move == 3) {
                if (y+1 <= 9 && random_walk[x][y+1] == '.') {
                    flag = 0;
                    y++;
                    random_walk[x][y] = letters[i];
                }
            }
        }
        if ((x-1 < 0 || random_walk[x-1][y] != '.') && (x+1 > 9 || random_walk[x+1][y] != '.') &&
            (y-1 < 0 || random_walk[x][y-1] != '.') && (y+1 > 9 || random_walk[x][y+1] != '.'))
            break;
    }

    for (i = 0; i < N; i++) {
        for (j = 0; j < N; j++)
            printf("%c", random_walk[i][j]);
        putchar('\n');
    }

    return 0;
}

```