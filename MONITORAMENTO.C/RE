#include <stdio.h>

int main() {
    float limite_temp;
    float temp;
    float soma_temp = 0.0;
    float maior_temp, menor_temp;

    int total_leituras = 0;
    int acima_limite = 0;
    int consecutivas_acima = 0;

    printf("==== SISTEMA DE MONITORAMENTO INDUSTRIAL ====\n");

    // Solicita e valida o limite de temperatura
    do {
        printf("Digite o limite de temperatura: ");

        if (scanf("%f", &limite_temp) != 1) {
            printf("Entrada invalida. Insira um valor numerico.\n");

            while (getchar() != '\n');

            continue;
        }

        if (limite_temp <= 0) {
            printf("O limite de temperatura deve ser maior que 0 graus.\n");
        }

    } while (limite_temp <= 0);

    // Recebe e processa as temperaturas do sensor
    printf("\nDigite a temperatura ou 000 para encerrar manualmente.\n");

    while (1) {
        printf("Temperatura %d: ", total_leituras + 1);

        if (scanf("%f", &temp) != 1) {
            printf("Entrada invalida. Digite um valor numerico.\n");

            while (getchar() != '\n');

            continue;
        }

        // Condicao para parar o monitoramento manualmente
        if (temp == 000) {
            printf("\nMonitoramento encerrado.\n");
            break;
        }

        // Atualiza a maior e a menor temperatura
        if (total_leituras == 0) {
            maior_temp = temp;
            menor_temp = temp;
        } else {
            if (temp > maior_temp) {
                maior_temp = temp;
            }

            if (temp < menor_temp) {
                menor_temp = temp;
            }
        }

        // Soma as temperaturas e conta as leituras
        soma_temp += temp;
        total_leituras++;

        // Verificacao de seguranca
        if (temp > limite_temp) {
            acima_limite++;
            consecutivas_acima++;

            printf("ALERTA: Temperatura acima do limite! ");
            printf("(%d/3 leituras consecutivas)\n", consecutivas_acima);

        } else {
            // Reinicia a contagem quando a temperatura
            // nao estiver acima do limite
            consecutivas_acima = 0;
        }

        // Encerra automaticamente com 3 temperaturas
        // consecutivas acima do limite
        if (consecutivas_acima == 3) {
            printf("\nALERTA: 3 temperaturas consecutivas acima do limite detectadas!\n");
            printf("Desligamento automatico do sistema ativado.\n");
            break;
        }
    }

    // Relatorio final
    printf("\n=========================================\n");
    printf("             RELATORIO FINAL             \n");
    printf("=========================================\n");

    if (total_leituras > 0) {
        float media_temp = soma_temp / total_leituras;
        float percentual = (acima_limite * 100.0) / total_leituras;

        printf("Total de leituras validas realizadas: %d\n", total_leituras);
        printf("Media das temperaturas: %.2f graus\n", media_temp);
        printf("Maior temperatura registrada: %.2f graus\n", maior_temp);
        printf("Menor temperatura registrada: %.2f graus\n", menor_temp);
        printf("Quantidade de leituras acima do limite: %d\n", acima_limite);
        printf("Percentual acima do limite: %.2f%%\n", percentual);

    } else {
        printf("Nenhuma leitura valida foi registrada.\n");
    }

    printf("=========================================\n");

    return 0;
}
