#include<pthreads.h>
#include<stdlib.h>

static int a = 10;
static int b = 5;


void * add(void * )
{
 
 int  sum = a +b ;
 printf("The sum is:  %d\n" , sum); 

}


void * mul(void * )
{
 
 int  mul = a * b ;
 printf("The product is:  %d\n" , mul); 

}


void * div(void * )
{
 
 int  di = a +b ;
 printf("The division is:  %d\n" , di); 

}


int main()
{

 pthread_t t1;
 pthread_t t2;
 pthread_t t3;

 pthread_create(&t1 , NULL , add , NULL  );
 pthread_create(&t2 , NULL , mul , NULL  );
 pthread_create(&t3 , NULL , div , NULL  );

 pthread_join(t1 , NULL);
 pthread_join(t2 , NULL);
 pthread_join(t3 , NULL);
 
  
 return 0;
}