# Banking-management-System
#include <stdio.h>
#include<conio.h>
#include<stdlib.h>
int list();
void deposit();
void last();
void transfer();
void withdraw();
void checkDetail();
int TotalAmount=1000,Amount,Amo,TR,TotalDeposit=0,TotalWith=0,TotalTR=0;
int Acc;
char a[50];
void main() 
{
    printf("\nEnter your name:");
    gets(a);
    printf("\nEnter your Account number:");
    scanf("%d",&Acc);
 while (1)
 {
   
 switch(list())
 {
     case 1:
            deposit();
            TotalDeposit+=Amount;
            break;
     case 2:
           withdraw();
           if(Amo<=TotalAmount)
           TotalWith+=Amo;
           break;
     case 3:
            transfer();
            if(TR<=TotalAmount)
            TotalTR+=TR;
            break;
     case 4:
           checkDetail();
           break;
     case 5:
           
           last();
           getch();
           exit(0);
     default:
     printf("\nInvalid choice");
 }//end of switch
  getch();
 }//end of while
}
int list()
{
    int ch;
    printf("\n1. Deposit Amount: ");
    printf("\n2. Amount Withdrawn: ");
    printf("\n3. Amount Transfer: ");
    printf("\n4. Check Details:");
    printf("\n5.EXIT:");
    printf("\nEnter Your Choice:");
    scanf("%d",&ch);
    return (ch);
}
void deposit()
{
    printf("\nEnter the amount you want to deposit:");
    scanf("%d",&Amount);
    TotalAmount+=Amount;
}
void withdraw()
{
    printf("\nEnter the amount you wish to withdraw:");
    scanf("%d",&Amo);
    if(Amo<=TotalAmount)
    TotalAmount-=Amo;
    else
    printf("\nLess amount withdraw is not possible");
}
void transfer()
{
    printf("\nEnter the amount you want to transfer");
    scanf("%d",&TR);
    if(TR<=TotalAmount)
    TotalAmount-=TR;
    else
    printf("\nLess amount transfer is not possible:");
}

void checkDetail()
{
    printf("Total Amount=%d",TotalAmount);
    printf("\nTotal Deposited Amount=%d",TotalDeposit);
    printf("\nTotal Withdrawn Amount=%d",TotalWith);
    printf("\nTotal Transfered Amount=%d",TotalTR);
}
void last()
{
    printf("\n*****************************************************\n");
    printf("\nYour Name=%s,a");
    printf("\nAccount Number=%d",Acc);
    printf("Total Amount=%d",TotalAmount);
    printf("\nTotal Deposited Amount=%d",TotalDeposit);
    printf("\nTotal Withdrawn Amount=%d",TotalWith);
    printf("\nTotal Transfered Amount=%d",TotalTR);
    printf("\n\n*******THANK YOU******");
}
