#include <stdio.h>
#include <string.h>

const int MAX = 256;

int fnHorspool(char string[], char pattern[],int []);
void fnGenShiftTable(char *,int []);

int main(void)
{
	char text[MAX];
	char pattern[MAX];
    	int shiftTable[MAX];
	int found;
	puts("Enter the source string : ");
	gets(text);
	puts("Enter the pattern string : ");
	gets(pattern);
	
	fnGenShiftTable(pattern,shiftTable);
	found = fnHorspool(text,pattern,shiftTable);

	if(found==-1)
		puts("\nMatching Substring not found.\n");
	else
		printf("\nMatching Substring found at position: %d\n",found+1);

	return 0;
}
void fnGenShiftTable(char p[], int t[])
{
	int m, i, j;

	m = strlen(p);

	for(i=0; i<MAX; i++)
	{
		t[i]=m;
	}

	for(j=0; j<m-1; j++)
	{
		t[p[j]] = m-1-j;
	}
}

int fnHorspool(char s[],char p[],int t[])
{
	int i, n, m, k;

	n = strlen(s);
	m = strlen(p);
	i = m-1;
	while(i<n)
	{
		k = 0;
		while((k<m)&&(p[m-1-k]==s[i-k]))
			k++;

		if (k == m)
			return i-m+1;
		else
			i = i+t[s[i]];
	}

	return -1;
}
ALGORITHM:
ALGORITHM Horspool(P[0…m-1], T[0…n-1])
//Implement Horspool’s algorithm for string matching
//Input: Pattern P[0…m-1] and text T[0…n-1]
//Output: The position of first matching, if successful, otherwise, -1
ShiftTable(P[0…m-1])
i←m-1
while i ≤ n-1 do
k ← 0
while k ≤ m-1 and P[m-1-k] ==T[i-k]
k ← k+1
if k==m
return i-m+1
else
i ← i+ Table[T[i]]
return -1
