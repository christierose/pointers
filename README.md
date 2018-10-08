//Christie Carranza
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int main()
{
int a[4][6], i, j;
srand(time(NULL));
for(i = 0; i < 4; i++)
for(j = 0; j < 6; j++)
a[i][j] = rand() % 56 + 17;

for(i = 0; i < 4; i++)
{
for( j = 0; j < 6; j++)
printf("%i ", *((int *)a+i*6+j));
printf("\n");
}

int sum = 0;
for(i = 0; i < 6; i++)
sum += *((int *)a+6+i);
printf("The sum of the second row of values: %i\n", sum);
  

sum = 0;
for(i = 0; i < 4; i++)
sum += *((int *)a+i*6+2);
printf("The sum of the third column of values: %i\n", sum);
int max = **a;
for( i = 0; i < 3; i++)
for(j = 0; j < 6; j++)
if(*((int *)a+6*i+j) > max)
max = *((int *)a+6*i+j);

printf("The maximum of the first three rows of values: %i\n", max);
  

int min = **(a+2);
for(i = 0; i < 4; i++)
for(j = 0; j < 4; j++)
{
if(*((int *)a+(6*i+j)+2) < min)
min = *((int *)a+(6*i+j)+2);
}
printf("The minimum of the last four columns of values: %i\n", min);   
}
