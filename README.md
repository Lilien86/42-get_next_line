# get_next_line

Ce projet consiste en l'implémentation de la fonction `get_next_line`, une fonction qui lit une ligne d'un fichier descripteur de fichier ou d'un flux d'entrée standard.

## Fonctionnement

La fonction `get_next_line` permet de lire une ligne (jusqu'à un caractère de nouvelle ligne) à partir d'un fichier descripteur de fichier (file descriptor) et de stocker cette ligne dans une chaîne de caractères allouée dynamiquement. À chaque appel de la fonction, la ligne suivante du fichier est lue jusqu'à ce qu'une nouvelle ligne soit trouvée ou que la fin du fichier soit atteinte.

## Instalation

1. Clonez ce référentiel sur votre machine locale.
	```bash
	https://github.com/Lilien86/42-get_next_line.git
	```
2. Compilez le programme avec les fichiers source de la fonction (et vortre propre main.c)
	```bash
	cc get_next_line.c get_next_line.h get_next_line_utils.c main.c
	```
## Utilisation

1. Incluez le fichier d'en-tête get_next_line.h et fcntl.h
	```c
	#include "get_next_line.h"
	#include "<fcntl.h>"
	```
2. Utilisez la fonction get_next_line
	```c
	int main() {
    int fd = open("exemple.txt", O_RDONLY);
    char *line;

    while (get_next_line(fd, &line) > 0) {
        // Traitement de la ligne lue
        printf("Ligne lue : %s\n", line);
        free(line);
    }

    close(fd);
    return 0;
	}
	```

