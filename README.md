/*# APS-Progama-o-estruturada-*/

#include <stdio.h> #include <stdlib.h> #include <locale.h> #include <time.h>

float soma_vet(float x[], int cont); void num_aleatorio(float x[]);

float soma_vet (float x[], int cont) { static float soma_auxiliar; int auxiliar;

if (cont<10 ){
	auxiliar= x[cont];
	if (auxiliar%2 == 0){
		soma_auxiliar += x[cont]; 
		cont++;
		soma_vet(x, cont);
	} else {
		cont++;
		soma_vet(x, cont);
	}
} else {
	
	auxiliar=soma_auxiliar;
	soma_auxiliar=0;
	return auxiliar;
	
}
}

void num_aleatorio (float x[]){ int contador=0;

for (contador; contador<=10;contador++){
	x[contador] = rand() % 50;
	printf("%.1f | ", x[contador]);
	
	
}
}

int main (){

float vet[10], soma = 0, soma_maior = 0; int i=1, vetor_maior=0; srand(time(NULL));

	for (i; i<=5; i++){	
			printf("\n %d* Vetor: ", i);
			num_aleatorio(vet);
			soma = soma_vet(vet, 0);
			if (soma > soma_maior){
				soma_maior = soma;
				vetor_maior = i;
			}
			printf(" \n Soma dos numeros pares do vetor %d: %.1f\n", i, soma);
			printf("\n----\n");
	}
	
	printf("\n Maior soma de numero pares: \n Vetor %d:  %1.f", vetor_maior, soma_maior);
}

