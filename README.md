# SETS-UNION-INTERSECTION-SYMMETRIC-DIFFERENCE-SUBTRACTION
Sets union , intersection, symmetric difference and subtraction between two sets program in C language without using hashing .
//VIGHNESH TIWARI 4252 SE IT ARMY INSTITUTE OF TECHNOLOGY,PUNE,INDIA
#include<stdio.h>                        //CR7VIGGY GITHUB PROFILE
#include<conio.h>
void insc(int x[], int a , int y[] , int b );
void unin(int x[], int a , int y[] , int b);
void sdiff(int x[], int a , int y[] , int b);
void sub(int x[], int a , int y[] , int b);
main()
{
	int a,b,i,j,k,m;
	printf("enter the size of ur first and second set array");
	scanf("%d %d",&a,&b);
	int x[a],y[b];
	printf("enter nos in set A");
	for(i = 0 ; i < a ; i++)
	scanf("%d",&x[i]);
	printf("enter nos in set B");
	for(i = 0 ; i< b ; i++)
	scanf("%d",&y[i]);
	
	do
	{
		printf("\npress 1 : union of sets\npress 2 : intersection of sets\npress 3 : to find symmetric difference between sets \n press 4 : to sub A - B and B - A\npress 5 to exit");
		scanf("%d",&m);
		
	
		
		switch(m)
		{
			case 1 : unin(x,a,y,b); break;
			case 2 : insc(x,a,y,b); break;
			case 3 : sdiff(x,a,y,b);break;
			case 4 : sub(x,a,y,b);break;
			case 5 : break;
		}
	}
while(m!=5);
     
}
    
//intersection function
void insc(int x[], int a , int y[] , int b )
{
	int c = 0,i,j;
	int z[c];
	for(i = 0 ; i < a ; i++)
		{
			for(j = 0 ; j < b ; j++)
			
				if(x[i] == y[j])
				{
					z[c] = x[i];
				    c++;
				}
				
		}
		
		for(i = 0 ; i < c ; i++)
		{
			for(j = i+1 ; j < c ; j++)
			{
				if(z[i]==z[j])
				{
					z[i] = NULL;
				}
			}
		}
		for(i = 0 ; i < c ; i++)
		{
			if(z[i] != NULL)
			printf("%d",z[i]);
	    }
}

//union function
void unin(int x[], int a , int y[] , int b)
{
	int c=a+b,i,j,d=0,temp = 0;
	int z[c];
	
	for(i = 0 ; i < a ; i++)
	{
		z[i] = x[i];
	}
	for(i = 0 ; i < b ; i++)
	{
		z[a+i] = y[i];
	}
	
	//sorting z[c] in ascending order
	for(i = 0 ; i < c ; i++)
	{
		for(j = i+1 ; j < c ;j++)
		{
			if(z[i] > z[j])
			{
				temp = z[i];
				z[i] = z[j];
				z[j] = temp;
			}
		}
	}
	
	for(i = 0 ; i < c ; i++)
	{
		for(j = i+1 ; j < c ; j++)
		if(z[j]==z[i])
		z[j]=NULL;
		
	}
		
	for(i = 0 ; i < c ; i++)
	if(z[i]!=NULL)
	printf("%d",z[i]);
	
}

//symmetric difference function 
void sdiff(int x[], int a , int y[] , int b)
{
	
	int i,j,k,count=0;
  	
  	for(i = 0 ; i < a ; i++)
  	{
  		for(j = 0 ; j < b ; j++)
  		{
  			if(x[i] == y[j])
  			{
  				count++;
			}
			  
		}
		  if(count!=1)
		  {
		  		printf("%d  ",x[i]);
		  }
		  count = 0;
	}
	  
	  	for(i = 0 ; i < b ; i++)
  		{
  			for(j = 0 ; j < a ; j++)
  			{
  				if(y[i] == x[j])
  				{
  					count++;
				}
			  
		 	}
		  if(count!=1)
		  {
		  	printf("%d  ",y[i]);
		  }
		  count = 0;
	
		}
		
}

//subtraction function
void sub(int x[], int a , int y[] , int b)
{
	int i,j,k,m,count=0;
	do
	{
	
		printf("press 1 to find A - B \npress 2 to find B - A\npress 3 to exit");
		scanf("%d",&m);
		
		switch(m)
		{
			case 1 : 	        for(i = 0 ; i < a ; i++)
							  	{
							  		for(j = 0 ; j < b ; j++)
							  		{
							  			if(x[i] == y[j])
							  			{
							  				count++;
										}
										  
									}
									  if(count!=1)
									  {
									  		printf("%d  ",x[i]);
									  }
									  count = 0;
								}break;
								
		    case 2 :            for(i = 0 ; i < b ; i++)
						  		{
						  			for(j = 0 ; j < a ; j++)
						  			{
						  				if(y[i] == x[j])
						  				{
						  					count++;
										}
									  
								 	}
								  if(count!=1)
								  {
								  	printf("%d  ",y[i]);
								  }
								  count = 0;
							
								}break;
		    
		    case 3 : break;
		}
	}
	while(m!=3);
}
