#include <stdio.h>

int main() {
   int z[2][2];
   int i, j;
   int m1, m2, m3, m4 , m5, m6, m7;
   int x[2][2];
   int y[2][2];

   // Input for the first matrix x
   printf("Enter the elements of the first matrix (2x2):\n");
   for(i = 0; i < 2; i++) {
      for(j = 0; j < 2; j++) {
         scanf("%d", &x[i][j]);
      }
   }

   // Input for the second matrix y
   printf("Enter the elements of the second matrix (2x2):\n");
   for(i = 0; i < 2; i++) {
      for(j = 0; j < 2; j++) {
         scanf("%d", &y[i][j]);
      }
   }

   printf("\nThe first matrix is\n");
   for(i = 0; i < 2; i++) {
      printf("\n");
      for(j = 0; j < 2; j++)
         printf("%d\t", x[i][j]);
   }
   printf("\nThe second matrix is\n");
   for(i = 0; i < 2; i++) {
      printf("\n");
      for(j = 0; j < 2; j++)
         printf("%d\t", y[i][j]);
   }
   m1= (x[0][0] + x[1][1]) * (y[0][0] + y[1][1]);
   m2= (x[1][0] + x[1][1]) * y[0][0];
   m3= x[0][0] * (y[0][1] - y[1][1]);
   m4= x[1][1] * (y[1][0] - y[0][0]);
   m5= (x[0][0] + x[0][1]) * y[1][1];
   m6= (x[1][0] - x[0][0]) * (y[0][0]+y[0][1]);
   m7= (x[0][1] - x[1][1]) * (y[1][0]+y[1][1]);
   z[0][0] = m1 + m4- m5 + m7;
   z[0][1] = m3 + m5;
   z[1][0] = m2 + m4;
   z[1][1] = m1 - m2 + m3 + m6;
   printf("\nProduct achieved using Strassen's algorithm \n");
   for(i = 0; i < 2 ; i++) {
      printf("\n");
      for(j = 0; j < 2; j++)
         printf("%d\t", z[i][j]);
   }
   return 0;
}

ALGORITHM:
Algorithm: Matrix-Multiplication (X, Y, Z) 
for i = 1 to p do 
   for j = 1 to r do 
      Z[i,j] := 0 
      for k = 1 to q do 
         Z[i,j] := Z[i,j] + X[i,k] × Y[k,j] 
