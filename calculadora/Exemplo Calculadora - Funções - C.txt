Exemplo Calculadora (Funções)

Calculadora.c

#include <stdio.h>
#include <stdlib.h>
#include "calculadora.h"


int somar(int a, int b){
    return a + b;
}

int subtrair(int a, int b){
    return a - b;
}

int multiplicar(int a, int b){
    return a * b;
}

int dividir(int a, int b){
    if(b){
        return a / b;
    }
    printf("Erro de divisão por zero");
    exit(-1);
}



Calculadora.h

/**
* Módulo: calculadora.h
 * Descrição: calculadora básica com as 04 operações:
 * somar, subtrair, multiplica e diviir.
 * Criada por: Maromo, em 17 de abril de 2023
*/

/**
 * Função somar: realiza a soma de dois valores inteiros
 * @param a  primeiro valpr
 * @param b  segundo valor
 * @return  retorna a soma do primeiro valor + o segundo valor
 */
int somar(int a, int b);

int subtrair(int a, int b);

int multiplicar(int a, int b);

int dividir(int a, int b);


Main.c


#include <stdio.h>
#include "calculadora.h"
int main() {
    int x, y, opc;
    do{
        //menu principal
        printf("Menu Principal\n");
        printf("1. Somar\n");
        printf("2. Subtrair\n");
        printf("3. Multiplicar\n");
        printf("4. Dividir\n");
        printf("5. Fim do programa\n");
        printf("Escolha sua opcao");
        scanf("%d", &opc);
        if(opc < 1 || opc > 5) continue;
        if(opc != 5){
            printf("Digite primeiro valor\n");
            scanf("%d", &x);
            printf("Digite segundo valor\n");
            scanf("%d", &y);
        }
        switch (opc) {
            case 1:
               printf("Resultado da soma: %d\n", somar(x, y));
               break;
            case 2:
                printf("Resultado da subtracao: %d \n", subtrair(x, y));
                break;
            case 3:
                printf("Resultaado da multiplicação: %d \n", multiplicar(x, y));
                break;
            case 4:
                printf("Resultado da divisao: %d \n", dividir(x, y));
                break;
            case 5:
                printf("Fim do programa");
        }
    }while(opc != 5);
    return 0;
}