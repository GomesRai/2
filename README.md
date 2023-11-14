# 2


#include <stdio.h>

void cadastro();
void salvarDados();

int main(void) {
    cadastro();
    salvarDados();
    return 0;
}

void cadastro() {
    char nome[50];
    int continuar;

    FILE *arquivo;
    arquivo = fopen("dados.txt", "w"); 

    if (arquivo == NULL) {
        printf("Erro ao abrir o arquivo.\n");
        return;
    }

    do {
        printf("Digite o nome: ");
        scanf("%s", nome);
        fprintf(arquivo, "Nome: %s\n", nome);

    } while (continuar == 1);

    fclose(arquivo);
}

void salvarDados() {
    char nome[50];
    int op, nota;

    FILE *arquivo;
    arquivo = fopen("dados.txt", "a"); 

    if (arquivo == NULL) {
        printf("Erro ao abrir o arquivo.\n");
        return;
    }

    printf("Voce gostou desse tema? 100 Anos da Semana de Arte Moderna (Digite 1 para sim ou 2 para nao): ");
    scanf("%d", &op);
    printf("Digite uma nota de 1 a 10 para a obra: ");
    scanf("%d", &nota);
    fprintf(arquivo, "Tema: 100 Anos da Semana de Arte Moderna, Opcao: %d, Nota: %d\n", op, nota);

    printf("Voce gostou desse tema? 150 Anos de Santos Dumont (Digite 1 para sim ou 2 para nao): ");
    scanf("%d", &op);
    printf("Digite uma nota de 1 a 10 para a obra: ");
    scanf("%d", &nota);
    fprintf(arquivo, "Tema: 150 Anos de Santos Dumont, Opcao: %d, Nota: %d\n", op, nota);

    printf("Voce gostou desse tema? Jogos Olimpicos de Paris 2024 (Digite 1 para sim ou 2 para nao): ");
    scanf("%d", &op);
    printf("Digite uma nota de 1 a 10 para a obra: ");
    scanf("%d", &nota);
    fprintf(arquivo, "Tema: Jogos Olimpicos de Paris 2024, Opcao: %d, Nota: %d\n", op, nota);

    printf("Voce gostou desse tema? Tokyo 2020 (Digite 1 para sim ou 2 para nao): ");
    scanf("%d", &op);
    printf("Digite uma nota de 1 a 10 para a obra: ");
    scanf("%d", &nota);
    fprintf(arquivo, "Tema: Tokyo 2020, Opcao: %d, Nota: %d\n", op, nota);

    fclose(arquivo);

    printf("Dados salvos com sucesso!\n");
}
