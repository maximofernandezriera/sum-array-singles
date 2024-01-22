# Kata: Sum of Array Singles : https://www.codewars.com/kata/59f11118a5e129e591000134

## Introducción
Sum of Array Singles" ES un desafío de manipulación de arrays. 

# El objetivo es encontrar y sumar los números que aparecen una sola vez en un array.

## Descripción del Problema
Se proporciona un array de números, donde algunos aparecen dos veces y otros una sola vez. El objetivo es calcular la suma de los números que aparecen una sola vez.

## Pseudocódigo

      función sumaDeSingles(array)
          suma = 0
          para cada número en array
              si el número aparece exactamente una vez en array
                  suma = suma + número
              fin si
          fin para
          devolver suma
      fin función

## Código en Java

    public class SumOfArraySingles {

    public static int sumOfSingles(int[] array) {
        int sum = 0;

        for (int i = 0; i < array.length; i++) {
            boolean isSingle = true;

            for (int j = 0; j < array.length; j++) {
                if (i != j && array[i] == array[j]) {
                    isSingle = false;
                    j = array.length; // Finaliza el bucle interno sin break
                }
            }

            if (isSingle) {
                sum += array[i];
            }
        }

        return sum;
    }

    public static void main(String[] args) {
        int[] exampleArray = {4, 5, 7, 5, 4, 8}; // Ejemplo de array
        int result = sumOfSingles(exampleArray);
        System.out.println("La suma de los números que aparecen una sola vez es: " + result);
    }
    
    }
