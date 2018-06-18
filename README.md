### Algo de trie par sélection sur plusieurs listes


```java
/**
*   Renvoie l'indice du plus grand élément du tableau
*
*   int tab[] :: tableau dans lequel on effectue la recherche
*   int taille :: taille du tableau
*
*   return int l'indice du plus grand élément
**/
int max(int versions[], int taille)
{
    // on considère que le plus grand élément est le premier
    int i=0, indice_max=0;

    // on parcourt la liste
    while (i<taille)
        // on compare le résultat de la première colonne
        if versions[i][c1] > versions[indice_max][c1]
            indice_max = i
        // si résultat égaux, on compare la deuxième colonne pour identifier la version la plus grande
        else if versions[i][c1] == versions[indice_max][c1]
            if versions[i][c1][c2] > versions[indice_max][c1][c2]
                indice_max = i
            // idem pour la colonne 3
            else if versions[i][c1][c2] == versions[indice_max][c1][c2]
                if versions[i][c1][c2][c3] > versions[indice_max][c1][c2][c3]
                    indice_max = i
        i++

    return indice_max;
}
```

```java
/**
*   Échange deux éléments d'un tableau
*
*   int tab[] :: tableau dans lequel on effectue l'échange
*   int x :: indice du premier élément
*   int y :: indice du second élément
*
*   return void
**/
void echanger(int tab[], int x, int y)
{
    int tmp;

    tmp = tab[x];
    tab[x] = tab[y];
    tab[y] = tmp;
}
```

```java
/**
*   Trie le tableau donné selon l'algorithme de tri par sélection
*
*   int tab[] :: tableau à trier
*   int taille :: taille du tableau
*
*   return void
**/
void tri_selection(int tab[], int taille)
{
    int indice_max;

    // à chaque tour de boucle, on va déplacer le plus grand élément
    // vers la fin du tableau, on diminue donc à chaque fois sa taille
    // car le dernier élément est obligatoirement correctement
    // placé (et n'a donc plus besoin d'être parcouru/déplacé)

    for(; taille > 1 ; taille--) // tant qu'il reste des éléments non triés
    {
        indice_max = max(tab, taille);

        echanger(tab, taille-1, indice_max); // on échange le dernier élément avec le plus grand
    }
}
```
