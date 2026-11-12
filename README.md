# trabalho de crud

#include <stdio.h>
#include <string.h>
#include <stdlib.h>

char prod[100][100];
float valor[100];
int quant = 0;
int num;
int codigo;

void menu(){
	printf("\n=====MENU=====");
	printf("\nDigite 1 para cadastrar um produto");
	printf("\nDigite 2 para listar os produtos cadastrados");
	printf("\nDigite 3 para consultar um item cadastrado");
	printf("\nDigite 4 para excluir um item cadastrado");
	printf("\nDigite 0 para sair\n");
}

void cadastro(){
	system("cls");
    if(quant < 100){
        getchar();

        printf("\nDigite o nome do produto: ");
        fgets(prod[quant], 100, stdin);
        prod[quant][strcspn(prod[quant], "\n")] = '\0';
        printf("Digite o valor do produto: ");
        scanf("%f", &valor[quant]);
        
        quant++;
        printf("\nProduto cadastrado");
    }
    else{
        printf("\nLimite de produtos atingido!");
    }
}

void lista(){
	system("cls");
	if(quant == 0){
		printf("\nNenhum produto cadastrado");
	}
	else{
		printf("\nProdutos cadastrados:\n");
		for(int i = 0; i < quant; i ++){
			printf("%i - %s - R$%.2f\n", i + 1, prod[i], valor[i]);
		}
	}
}

void consulta(){
	system("cls");
	printf("\nDigite o numero do produto:\n");
    scanf("%d", &codigo);
    if(codigo > 0 && codigo <= quant){
        printf("\nProduto: %s", prod[codigo - 1]);
        printf("\nValor: R$%.2f", valor[codigo - 1]);
    }
    else{
        printf("\nProduto nao encontrado!");
    }
}

void excluir(){
	system("cls");
    printf("\nDigite o numero do produto que deseja excluir:\n");
    scanf("%d", &codigo);

    if(codigo > 0 && codigo <= quant){

        for(int i = codigo - 1; i < quant - 1; i++){
            strcpy(prod[i], prod[i + 1]);
            valor[i] = valor[i + 1];
        }

        quant--;

        printf("\nProduto excluido!");
    }
    else{
        printf("\nProduto nao encontrado!");
    }
}
int main(){
	do{
		menu();
		scanf("%i", &num);
		
		switch(num){
			case 1:
				cadastro();
				break;
				
			case 2:
				lista();
				break;
				
			case 3:
				consulta();
				break;
				
			case 4:
				excluir();
				break;
				
			case 0:
				printf("Saindo...");
				break;
				
			default:
				system("cls");
				printf("Opcao invalida");
		}
	}
	while(num != 0);
	
	return 0;
}
	}
	
	return 0;
}
