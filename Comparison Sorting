#include<stdio.h>

void countingsort(int a[], int n) {
   int i, j;
   int output[15], c[100];
   
   for (i = 0; i < 100; i++)
      c[i] = 0;

   for (j = 0; j < n; j++)
      ++c[a[j]];

   for (i = 1; i <= 99; i++)
      c[i] += c[i-1];

   for (j = n-1; j >= 0; j--) {
      output[c[a[j]] - 1] = a[j];
      --c[a[j]];
   }

   printf("The Sorted array is: ");
   for (i = 0; i < n; i++)
      printf("%d ", output[i]);
}

int main(){
   int n = 5, i;
   int a[15] = {12, 32, 44, 8, 16};
   countingsort(a, n);
   
   return 0;
}
