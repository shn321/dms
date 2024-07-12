# dms
//universal quantification
#include<stdio.h>
int main()
{
    int A[100],i,n,uq=0;
    printf("\n ENTER THE NO OF ELEMENTS IN SET A=");
    scanf("%d",&n);
    printf("\n ENTER THE %d NO OF ELEMENTS=",n);
    for(i=0;i<n;i++)
        scanf("%d",&A[i]);
    for(i=0;i<n;i++)
    {
        if(A[i]%2==0)
            uq=1;
        else
            uq=0;
    }
    if(uq==1)
        printf_s("ALL/EACH ELEMENTS OF SET A ARE EVEN ARE UNIVERSAL QUANTIFIERS");
    else
        printf_s("SOME ELEMENTS OF SET A ARE EVEN ARE NOT UNIVERSAL QUANTIFIERS");
    return 0;
}

