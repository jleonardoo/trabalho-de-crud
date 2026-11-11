# trabalho de crud

#include <stdio.h>
#include <string.h>
#include <locale.h>
#include <stdlib.h>

struct aluno {
	int id;
	char nome[100];
	int idade;
	float nota;
};

int op = 0;

void menu(){
	
	printf("sistema crud\n");
	printf("[1] - cadastrar\n");
	printf("[2] - listar\n");
	printf("[3] - consutar\n");
	printf("[4] - atualizar\n");
	printf("[5] - excluir\n");
	printf("[6] - encerrar sistema\n");
	printf("selecione uma opcao:\n");
	scanf("%i", &op);
	
}

void cadastrar(struct aluno *estudante){
	// recebe ID
	
	// recebe NOME
	
	// recebe IDADE
	
	// recebe NOTA
	
}

int main(){
	
	while(op != 6){
		menu();
		
		switch(op){
			
			case 1:
				//cadastro
				break;
			case 2:
				//listar
				break;
			case 3:
				//consutar
				break;
			case 4:
				//atualizar
				break;
			case 5:
				//excluir
				break;
			case 6:
				printf("encerrando o siatema...");
				break;
			default:
				printf("opcao invalida!\n");
		}
	}
	
	return 0;
}
