#include <stdio.h>
#include <string.h>

int main()
{
    int a[100],b[100];
    int ans[200]={0};
    int i,j,tmp;
    char s1[101],s2[101];
    scanf(" %s",s1);
    scanf(" %s",s2);
    int l1 = strlen(s1);
    int l2 = strlen(s2);
    for(i = l1-1,j=0;i>=0;i--,j++)
    {
        a[j] = s1[i]-'0';
    }
    for(i = l2-1,j=0;i>=0;i--,j++)
    {
        b[j] = s2[i]-'0';
    }
    for(i = 0;i < l2;i++)
    {
        for(j = 0;j < l1;j++)
        {
            ans[i+j] += b[i]*a[j];
        }
    }
    for(i = 0;i < l1+l2;i++)
    {
        tmp = ans[i]/10;
        ans[i] = ans[i]%10;
        ans[i+1] = ans[i+1] + tmp;
    }
    for(i = l1+l2; i>= 0;i--)
    {
        if(ans[i] > 0)
            break;
    }
    printf("Product : ");
    for(;i >= 0;i--)
    {
        printf("%d",ans[i]);
    }
    return 0;
}
ALGORITHM:

Step 1 : Multiply index i of B with all the indexes j of A. Add the product to value in Ans[k] where 0 <= i < L2, 0 <= j < L1, k = i+j.
Step 2 : Repeat step 1 till i = L2. (Picture how you multiply two large numbers on a paper).
Step 3 :
for each i in range(0,L1+L2)
TMP = X/10. X = X%10. Y = Y+TMP.
X = A[i]
Y = A[i+1]
TMP = temporary variable.
Step 4 : reverse the array Ans, and that will be the final product.
