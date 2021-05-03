# Algo_revision


## (EXO 1)Déterminer si la string passée en parametre d'une fonction est un palindrome.
 ex de palindrome : kayak, ressasser, sos, lol, racecar.
 
 => BONUS : Les caractères spéciaux, chiffres, espaces, majuscules devront être supprimés.
 
-> SOLUTION <details>
 
  
 
 
 ```js
 

 
 
 
// Un premier tableau avec le découpage des lettres que compose la string dans le sens "gauche -> droite".
var tab = [];
// Un second tableau pour le découpage dans le sens "droite -> gauche".
var tab_2 = [];


function palindrome(str) {


// On remplace les caractères spéciaux
str = str.replace(/[^0-9a-zA-Z.,''""" "]/gi, '')

// Boucle pour push dans le 1er tableau
for (let i = 0; i < str.length; i++)
  {
  tab.push(str[i]);
  
  }
  
// Boucle pour push dans le 2nd tableau
for (let i = str.length-1; i >= 0; i--)
  {
  tab_2.push(str[i]);
  
  }

  
// Comparaison des tableaux, si la valeur des 2 tableaux ne sont pas identiques, on sort de la boucle.
for (let y = 0; y < tab.length; y++)
  {
    if (tab[y] != tab_2[y])
    {
      return false;
    }
    else return true;
  }  
  

  
}



console.log(palindrome(""));


```
</details>

## (EXO 2)Fonction Search n' Destroy.
 
 Recherche dans un tableau les valeurs passées en paramètres et les supprime. Retourne un tableau des valeurs restantes.
 
 Exemple : SearchNDestroy([1, 2, 3, 1, 2, 3], 2, 3) = [1,1] (A supprimé tous les 2 et 3 de la liste et retourne le reste, ici 1 et 1)
 
 
 
 SOLUTION =>
 <details>
 
 
 ``` js
 
 function destroyer(arr,arg1,arg2) {
let tab = [];

  for (let i =0; i <=arr.length; i++)

    {
      if (arr[i] === arg1 || arr[i] === arg2)
      {
        delete (arr[i])
       
      }
     if (arr[i] != null)
     {
       tab.push(arr[i])
     }
  
    }
  
  return tab;
}

``` 
 
 </details>
 
)
##

Extrait de https://callicode.fr/pydefis/VitesseLumiere/txt

Données d'entrée = (997, 312, 663);

Histoire Luke, Obi-Wan, Han et Chewbacca sont sur le point de quitter Tatooine et partent pour Aldorande.

Mais ils sont pris en chasse par des croiseurs interstellaires de l'empire.

Le faucon millénium pourra distancer ses poursuivants dès qu'ils sera passé en vitesse lumière.

Obi-Wan et Luke pressent Han de calculer les coordonnées pour passer en vitesse lumière, mais Han leur explique :

Il faut un petit moment, le temps de définir les navi-composantes.
Il suffit d'une petite erreur de calcul et la trajectoire passe à travers une étoile ou bien on frôle une supernova et là, la ballade est terminée.
Calculer les navi-composantes n'est pas si simple.

Étant donné un point d'arrivée souhaité, donné par 3 valeurs x, y et z, le calcul des navi-composantes est fait par l'algorithme suivant (* est la multiplication et % est le reste de la division entière (modulo)):
```bash
initialiser x, y, et z
tant que 10 * x > y :
    x = (y * z) % 10000
    y = (3 * z) % 10000
    z = (7 * z) % 10000
afficher les navi-composantes finales : x, y, z
Le point d'arrivée (valeurs initiales de x, y et z) est donné en entrée du problème.

```
</details>

Attention
Si le calcul dure plus de 10000 pas de temps, alors les coordonnées du point d'arrivée seront considérées comme inaccessibles. La réponse attendue sera alors (-1,-1,-1).

Défi
Fournissez les navi-composantes obtenues par l'algorithme sous forme de tableau qui précède pour valider le défi et passer en vitesse lumière.


 
