# Ex. No : 2
# IMPLEMENTATION OF SYMBOL TABLE
## Register Number : 212223240037
## Date : 15/02/2024
# AIM :
To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol is inserted into symbol table along with its memory address.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8.	Stop the program. 
# PROGRAM
```
#include<stdio.h>
#include<conio.h> 
#include<ctype.h> 
#include<stdlib.h> 
#include<string.h> 
#include<math.h>
void main()
{
    int i=0,j=0,x=0,n,flag=0; 
    void *p,*add[5];
    char ch,srch,b[15],d[15],c;
    printf("Enter the Expression terminated by $:");
    while((c=getchar())!='$')
    {
        b[i]=c; i++;
    }
    n=i-1;
    printf("Given Expression:");
    i=0;
    while(i<=n)
    {
        printf("%c",b[i]); 
        i++;
    }
    printf("\n Symbol Table\n"); 
    printf("Symbol\taddr\t\ttype"); 
    while(j<=n)
    {
        c=b[j]; 
        if(isalpha(toascii(c)))
        {
            if(j==n)
            {           
                p=malloc(c); 
                add[x]=p;
                d[x]=c;
                printf("%c\t%d\tidentifier",c,p);
            }   
            else
            {
                ch=b[j+1];
                if(ch=='+'||ch=='-'||ch=='*'||ch=='=')
                {
                    p=malloc(c); 
                    add[x]=p;
                    d[x]=c; 
                    printf("\n%c\t%d\tidentifier\n",c,p); 
                    x++;
                }
            }
        } 
        j++;
    }
    printf("\n The symbol is to be searched"); 
    srch='B';
    for(i=0;i<=x;i++)
    {
        if(srch==d[i])
        {
            printf("\n Symbol Found"); 
            printf("\n%c @address %d\n",srch,add[i]); 
            flag=1;
        }
    }
    if(flag==0)
        printf("\nSymbol Not Found"); 
    getch();
}
```
# OUTPUT
![image](https://github.com/GnanendranN/Ex2-IMPLEMENTATION-OF-SYMBOL-TABLE-/assets/138955207/0a44ed0a-e057-4d1e-861c-be02a3eb7c75)

# RESULT
The program to implement a symbol table is executed and the output is verified.
