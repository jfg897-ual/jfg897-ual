#include <stdio.h>

int main() {
    // Definir colores y sus valores asociados
    char colores[10][10] = {"negro", "marron", "rojo", "naranja", "amarillo",
                            "verde", "azul", "violeta", "gris", "blanco"};
    int valores[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};

    // Pedir al usuario que ingrese los colores de las 3 bandas
    char color1[10], color2[10], color3[10];
    printf("Ingrese el color de la primera banda: ");
    scanf("%s", color1);
    printf("Ingrese el color de la segunda banda: ");
    scanf("%s", color2);
    printf("Ingrese el color de la tercera banda: ");
    scanf("%s", color3);

    // Buscar los valores asociados a los colores ingresados
    int valor1 = -1, valor2 = -1, multiplicador = -1;
    for (int i = 0; i < 10; i++) {
        if (strcmp(color1, colores[i]) == 0) {
            valor1 = valores[i];
        }
        if (strcmp(color2, colores[i]) == 0) {
            valor2 = valores[i];
        }
        if (strcmp(color3, colores[i]) == 0) {
            multiplicador = i;
        }
    }

    // Verificar que se encontraron los valores para realizar el cálculo
    if (valor1 == -1 || valor2 == -1 || multiplicador == -1) {
        printf("Error: colores de banda no válidos.\n");
    } else {
        // Calcular el valor de la resistencia
        int resistencia = (valor1 * 10 + valor2) * pow(10, multiplicador);

        // Mostrar el resultado al usuario
        printf("El valor de la resistencia es: %d ohmios\n", resistencia);
    }

    return 0;
}
