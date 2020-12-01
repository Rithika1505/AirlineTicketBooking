/***Business Class***/
//code
#include <stdio.h>
#include<stdlib.h>
#include<string.h>
int right=2;
int left=2;
int mid=3;
int row=12;
int col;
/***Creating a Structure array for storing the details of passengers(Business class)***/
struct details
{
    char book[100];
    int tp,rpos,cpos;
    int meal;
}det[100];
char a[100][100];char b[100][100]={'E'};
int count=0;int k=0;
/***Booking of tickets***/
void BookingHandling(int ro,char co)
{
	int i,j;static int ticcount=0,sur=100;
	col=right+left+mid;
	for(i=0;i<row;i++)
	{
	    for(j=0;j<col;j++)
	    {
	        if(j==0||j==col-1)
	        a[i][j]='W';
	        else
	        a[i][j]='M';
	        b[i][j]='E';
	    }
	}
	for(i=0;i<row;i++)
	{
	    for(j=0;j<col;j++)
	    {
	        if(j==right||j==right-1||j==right+left||j==right+left+1)
	        a[i][j]='A';
	    }
	}
	    char book_id[100]="A101-B-000";//creating booking id based on the count of the number of tickets
	    int cost=2000;
	    int c=co-65;int r=ro;char no[10];
	    for(i=0;i<row;i++)
	    {
	        for(j=0;j<col;j++)
	        {
	            if(i==r&&j==c&&b[i][j]!='O')
	            {
	                if(a[i][j]=='W'||a[i][j]=='A')
	                cost=cost+100;
	                count++;
	                sprintf(no,"%d",count);
	                strcat(book_id,no);
	                det[k].rpos=i;
	                det[k].cpos=j;
	                b[i][j]='O';
	                printf("Successfully booked!\n");
	                ticcount++;
	            }
	       
	        }
	    }
	    strcpy(det[k].book,book_id);
	    det[k].tp+=cost;
	    if(ticcount>1){
	    det[k].tp+=sur;
	    sur+=100;
	    }
	}
/***Meal requirement for flight***/
	int Mealreq()
	{
	    char ch;int q;
	    scanf("Meal: Y/N\n%c",&ch);
	    if(ch=='Y')
	    {
	        printf("Enter the no of qty\n");
	        scanf("%d ",&q);
	        det[k].tp+=(200*q);
	        det[k].meal=1;
	    }
	    else
	    det[k].meal=0;
	}
/***Ticket Cancellation***/
	void TicketCancel(char*bookingid)
	{
	    int i,j;
	    for(i=0;i<k;i++)
	    {
	        if(strcmp(bookingid,det[i].book)==0)
	        {
	            b[det[i].rpos][det[i].cpos]='E';
	            int cancfee=det[i].tp-200;
	            det[i].tp-=cancfee;
	            printf("%d is deposited in your account deducting 200\n",det[i].tp);
	        }
	    }
	}
/***Seat Availablity***/
	void SeatAvl()
	{
	    int i,j;
	    for(i=0;i<row;i++)
	    {
	        for(j=0;j<col;j++)
	        {
	            printf("%c ",b[i][j]);
	        }
	        printf("\n");
	    }
	}
/***Displaying the no of seats booked with meals***/
	void seatMeal()
	{
	    int i;
	    for(i=0;i<k;i++)
	    {
	        if(det[i].meal==1)
	        {
	            printf("%d_%c\n",det[i].rpos,det[i].cpos+64);
	        }
	    }
	}
/***printing the passenger details based on booking id***/
	void print(char*bookingid)
	{
	    int i;
	    for(i=0;i<k;i++)
	    {
	        if(strcmp(bookingid,det[i].book)==0)
	        {
	            printf("%s %d_%c %d 101\n",det[i].book,det[i].rpos,det[i].cpos+64,det[i].meal);
	        }
	    }
	}
    int main()
    {
        int inputrow,i;char inputcol;int no;
        int choice;
        char bookingid[100];int fno;
        char class;
        printf("Enter the flight no\n");
        scanf("%d\n",&fno);
        printf("1.Booking\n2.Cancellation\n3.SeatAvailibity\n4.Meal ordered\n5.Display");
        do{
        printf("Enter the choice: ");
        scanf("%d\n",&choice);
        switch(choice)
        {
            case 1:
               printf("Welcome to Business class booking!\n");
               scanf("%c\n",&class);
               printf("Enter the no of seats\n");
               scanf("%d ",&no);
               for(int i=0;i<no;i++)
               {
                  printf("Enter the seat row and column: ");
                  scanf("%d %c\n",&inputrow,&inputcol);
                  BookingHandling(inputrow,inputcol);
                  Mealreq();
                  k++;
               }
               break;
            case 2:
               printf("Ticket Cancellation:\n");
               printf("Enter the booking id: ");
               scanf("%s\n",bookingid);
               TicketCancel(bookingid);
               break;
            case 3:
               printf("Seat Availablity\n");
               SeatAvl();
               break;
            case 4:
               printf("Seat nos for which meal ordered:\n");
               seatMeal();
               break;
            case 5:
               printf("Enter the booking id: ");
               scanf("%s\n",bookingid);
               print(bookingid);
               break;
            default:
               exit(0);
        } }while(choice!=0);
	return 0;
    }

