#include <stdio.h>

int main() {
    double credito, tasaInteres, interesAnual, totalIntereses = 0;
    double cuotaMensual, inversion;
    int años;

    printf("Ingrese monto del crédito: ");
    scanf("%lf", &credito);

    printf("Ingrese la tasa de interés: ");
    scanf("%lf", &tasaInteres);

    printf("Ingrese el número de años: ");
    scanf("%d", &años);

    printf("\nAño\tInterés\tCuota Mensual Anual\tInversión\n");

    double cuotaMensualAnual = credito / años; // Calcula la cuota 
               //mensual anual

    for(int i = 1; i <= años; i++) {
        interesAnual = (credito * tasaInteres) / 100;
        totalIntereses += interesAnual;

        cuotaMensual = cuotaMensualAnual - (totalIntereses / (credito 
           / 100)); // Calcula la cuota mensual
        credito -= cuotaMensualAnual; // Descuenta la cuota mensual 
                   //anual del crédito

        inversion = totalIntereses / 100 * 0.5; // Calcula la 
                 //inversión por cada 100 dólares de interés
        totalIntereses -= inversion * 100; // Resta la inversión del 
                   //total de intereses

        printf("%d\t%.2lf\t%.2lf\t\t\t%.2lf\n", i, interesAnual, cuotaMensual, inversion);
    }

    printf("\nTotal Intereses: %.2lf\n", totalIntereses);

    return 0;
}
