# CRIIBLE-MATH
 ce code en C permet d'afficher les nombres premiers jusqu'à le nombre saisi  ;
       
         #include <stdio.h>
            #include <stdbool.h>

     int main() {
        int K;

    // Lecture de K
    printf("Entrez un nombre K : ");
    scanf("%d", &K);

    // Vérification
    if (K< 2) {
        printf("Il n'y a pas de nombres premiers <= %d.\n", K);
        return 0;
    }

    bool estPremier[K + 1];

    // Initialisation : on suppose que tout est premier
    for (int i = 0; i <= K; i++) {
        estPremier[i] = true;
    }

    estPremier[0] = false;
    estPremier[1] = false;

    // Crible d'Ératosthène
    for (int i = 2; i * i <= K; i++) {
        if (estPremier[i]) {
            for (int j = i * i; j <= K; j += i) {
                estPremier[j] = false;
            }
        }
    }

    // Affichage des résultats
    printf("Les nombres premiers jusqu'a %d sont :\n", K);
    for (int i = 2; i <= K; i++) {
        if (estPremier[i]) {
            printf("%d ", i);
        }
    }
    printf("\n");
    printf("Merci!");
        return 0;
       }


    return 0;
}
