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



//Arithmetic series
#include <stdio.h>
int main()
{
 int i; float a,n,d,sum=0;
 printf(" Enter 1st no of series: \n");
 scanf("%f", &a);
 printf(" Enter total no's in series: \n");
 scanf("%f", &n);
 printf("Enter Common Difference: ");
 scanf("%f", &d);
 for (int i=0;i<n;i++)
 {
 sum = sum + a;
 a=a+d;
 }
 printf("sum of series A.P is :%f ",sum);
 return 0;
}



//sum of first 10 terms of sequence 1/n2
#include <stdio.h>
#include<math.h>
int main()
{
 int n,i;
 double sum=0.0,ser;
 printf("Enter the sum of the n terms of the sequence=");
 scanf("%d",&n);
 for(i= 1;i<= n; i++)
 {
     ser=1/pow(i,2);
     sum=sum+ser;
 }
    printf("sum of the first %d terms of the sequence is=%lf",n,sum);
    return 0;
}


//intersection of two sets
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int a[100],b[100],c[100],n1,n2,i,j,k=0;
    printf("enter number of element of set a=");
    scanf("%d",&n1);
    printf("enter %d number of elements of set a=",n1);
    for(i=0;i<n1;i++)
        scanf("%d",&a[i]);
    printf("enter %d number of elements of set b=");
    scanf("%d",&n2);
    printf("enter %d number of elements of set b=",n2);
    for(i=0;i<n2;i++)
    scanf("%d",&b[i]);
    for(i=0;i<n1;i++)
    {
        for(j=0;j<n2;j++)
        {
            if(a[i]==b[j])
            {
                c[k]=a[i];
                k++;
                break;
            }
        }
    }
    printf("\n intersection of set a and b is=");
    for(i=0;i<k;i++)
        printf("%d\t",c[i]);
}


//power set of a given set
#include<stdio.h>
#include<math.h>
void printpowerset(char*set,int set_size)
{
    unsigned int pow_set_size=pow(2, set_size);
    int counter,j;
    for(counter=0;counter<pow_set_size;counter++)
    {
        for(j=0;j<set_size;j++)
        {
            if(counter & (1<<j))
                printf("%c",set[j]);
        }
        printf("\n");
    }
}
int main()
{
    char set[]={'a','b','c'};
    printpowerset(set,3);
    return 0;
}



//factorial of a number using recursion
#include<stdio.h>
#include<conio.h>
long int factorial(int n);
int main() {
    int n;
    printf("Enter a positive integer: ");
    scanf("%d",&n);
    printf("Factorial of %d = %d", n, factorial(n));
    return 0;
}

long int factorial(int n) {
    if (n>=1)
        return n*factorial(n-1);
    else
        return 1;
}



//fibonacci series using recursion
#include <stdio.h>
int fibonacci(int n) {
   if(n == 0)
      return 0;
   else if(n == 1)
      return 1;
   else
      return (fibonacci(n-1) + fibonacci(n-2));
}

int main() {
   int n;

   printf("Enter the number of terms\n");
   scanf("%d", &n);

   printf("Fibonacci Series: ");
   
   for (int i = 0; i < n; i++) {
      printf("%d ", fibonacci(i));
   }
   
   return 0;
}


//tower of hanoi
#include <stdio.h>
#include <stdlib.h>

void towerOfHanoi(int n, char from_rod, char to_rod, char aux_rod)
{
    if (n == 1)
    {
        printf("\nMove disk 1 from rod %c to rod %c", from_rod, to_rod);
        return;
    }
    towerOfHanoi(n-1, from_rod, aux_rod, to_rod);
    printf("\nMove Disk %d from rod %c to rod %c", n, from_rod, to_rod);
    towerOfHanoi(n-1, aux_rod, to_rod, from_rod);
}

void main()
{
    int n = 4;
    towerOfHanoi(n,'A','C','B');

getch();
}



//binary search technique
#include<stdio.h>
#include<conio.h>
int main()
{
int i,first,last,middle,n,search,array[100];
printf("enter number of elements \n");
scanf("%d",&n);
printf("enter %d integers \n",n);
for(i=0;i<n;i++)
scanf("%d",&array[i]);
printf("Enter value to find\n");
scanf("%d",&search);
first=0;
last=n-1;
middle=(first+last)/2;
while(first<=last)
{
if (array[middle]<search)
first=middle+1;
else if(array[middle]==search)
{
printf("%d found at location %d.\n", search, middle+1);
break;
}
else
last=middle-1;
middle=(first+last)/2;
}
if (first>last)
printf("Not found! %d is not present in the list.\n", search);
return 0;
}


//merge sort technique
#include<stdio.h>
#include<conio.h>
int a[20];
void merge_sort (int[],int,int);
void merge (int[],int,int,int);
void main()
{
int arr[30],i,n;
printf("\nEnter no of elements");
scanf("%d",&n);
printf("\nEnter %d value",n);
for(i=0;i<n;i++)
scanf("%d",&arr[i]);
printf("\nBefore sorting elements are");
for(i=0;i<n;i++)
printf("%d ",arr[i]);
merge_sort(arr,0,n-1);
printf("\nAfter sorting elements are");
for(i=0;i<n;i++)
printf("%d ",arr[i]);
}
void merge_sort(int arr[],int f,int l)
{
int mid;
if(f<l)
{
mid =(f+l)/2;
merge_sort(arr,f,mid);
merge_sort(arr,mid+1,l);
merge(arr,f,mid,l);
}
}
void merge(int arr[],int low,int mid,int high)
{
int l1,l2,i;
for(l1=low,l2=mid+1,i=low;l1<=mid&&l2<=high;i++)
{
if (arr[l1]<=arr[l2])
a[i]=arr[l1++];
else
a[i]=arr[l2++];
}
while(l1<=mid)
a[i++]=arr[l1++];
while(l2<=high)
a[i++]=arr[l2++];
for(i=low;i<=high;i++)
arr[i]=a[i];
}
