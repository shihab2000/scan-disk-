# scan-disk-
#include<stdio.h>
void main()
{
	int a[30],n,i,j,head,seek,temp;
	printf("ENTER THE  NUMBER OF REQUEST : ");
	scanf("%d",&n);
	printf("ENTER THE HEAD POSITION : ");
	scanf("%d",&head);
	printf("ENTER THE SEQUENCE  :");
	for(i=1;i<=n;i++)
		scanf("%d",&a[i]);
	    a[n+1]=head;
	  a[0]=0;
	 
	 for(i=0;i<=n+1;i++)
	 {
		 for(j=i;j<=n+1;j++)
		 {
			 if(a[i]>a[j])
			 {
				 temp=a[i];
				 a[i]=a[j];
				 a[j]= temp;
			 }
		 }
	 }

    int hloc;

	
		 for(i=0;i<=n+1;i++)
	      {   			  
			  if(a[i]==head)
			      hloc=i;
		  }  
			   
		  for(i=hloc;i>0;i--)
		  {
			    printf("%d-->",a[i]);  
			    seek=seek+abs(a[i]-a[i-1]); 		        
		   }    
	     /*for(i=hloc+1;i<=n+1;i++)
			{
			  printf("%d-->",a[i]); 
			  if(i==hloc+1)
			     seek=seek+a[i];
			  else 
			     seek=seek+abs(a[i]-a[i-1]); 
	         }*/
 
       	printf("\n total seek time =%d",seek);
      

    
 
 }
