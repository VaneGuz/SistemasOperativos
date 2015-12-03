#include <stdio.h>
#include <pthread.h>
#define NUMTHREADS 200
#define MAXCNT 1000

//Variables globales-Compartidas entre hilos
double counter=0;

void*counting(void *);

int main(int argc, char const *argv[])
{
	pthread_t tid[NUMTHREADS];
	int i=0;

	for (i = 0; i < NUMTHREADS; ++i)
	{
		pthread_create(&tid[i],NULL,&counting, NULL);
	}
	for ( i = 0; i < NUMTHREADS; ++i)
	{
		pthread_join(tid[i],NULL);
	}
	printf("Contador puede estar en %d\n",MAXCNT*NUMTHREADS );
	printf("Valor del contador es %.0f\n", counter);


	return 0;
}

void* counting(void *unused){
	int i=0;
	for (i = 0; i < MAXCNT; ++i)
	{
		counter++;
	}
	return NULL;
}
