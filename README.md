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
 
 ## (EXO 3) Checker si une string (1er agrument (str), se termine par la string passée en 2nd argument (target).
 Exemple : confirmEnding("Bastian", "n") doit retourner TRUE;
 confirmEnding("Connor", "n") doit retourner FALSE.
 
 NE PAS UTILISER LA FONCTION NATIVE '.endsWith()'

SOLUTION =>

<details>
 
 ```js
 let tab = [];

let tab_2 = [];

function confirmEnding(str, target) {

  str = str.replace (' ','')
  for (let i = str.length-1; i >= 0; i--)
  {
    tab.push(str[i])
  }
  console.log(tab)

  for (let z = target.length-1; z >= 0; z--)

 
    {
      tab_2.push(target[z])
      
    }

 console.log(tab_2)

for (let y = 0; y < tab_2.length; y++)
  
  if (tab[y] != tab_2[y])
  {
    console.log(false)
    return false
  }
  console.log(true)
  return true;

  ```
  
</details>
  
}

## (EXO 4) CALCULATRICE JS

<details>
 
 ```js

 <div class="container">
            <div class="row">
                <FORM NAME='unFormulaire'>
                    <input type="number" name="nb1" class="input_element"></div>
                <label for ="operator"> </label>
                <select name="operators" value="operators" id="operators" size="3">

                    <!-- ICI L'OPTION RADION EST IMPORTANTE POUR AVOIR LA REMONTEE DE LA DONNEE SELECTIONEE-->

                    <option type="radio" type name ="addition" id="addition" value="addition">+</option>
                    <option value="soustraction">-</option>
                    <option value="division">/</option>
                    <option value="multiplication">X</option>

                </select>


                <input type="number" name="nb2" class="input_element_2">
                <button type="button" onclick="operations(unFormulaire)">Go !</button>
        
                </FORM>
                
              
              
              
            

        </div>
                
       
    


    <script>

      



            /* ON RECUPERE LES DONNEES GRACE A LA FONCTION OPERATION */



            function operations (unFormulaire) 
            {

                /* CREATION DE VARIBALES OU SONT STOCKES LES DONNEES DU FORMULAIRE */



                

                /* nb1 POUR L'INPUT_1 */

                let nb1 = parseInt(unFormulaire.nb1.value);

                /* parseInt pour forcer la conversion de la string renvoyée par le formulaire en donnée de type NUMBER ex:("12" -> 12) */
                console.log (nb1);


                /* nb2 POUR L'INPUT_2 */

                let nb2 = parseInt(unFormulaire.nb2.value)
                console.log (nb2);



                /* operator POUR LA SELECTION RADIO DE LOPERATION SOUHAITEE */

                let operator = (unFormulaire.operators.value);
                console.log(operator);



                /* SWITCH POUR APPLIQUER LA FONCTION SOUHAITEE EN LIEN AVEC LE CHOIX DE L UTILISATEUR */
                

                /* SWITCH SUR OPERATOR POUR CONDITIONNER L APPEL A LA FONCTION SOUHAITEE */
            
              switch (operator) {
                  
                case 'soustraction':  /* LA DONNEE RENVOYEE N'EST PAS UNE STRING MAIS JS FAIT LA CONVERSION AUTO ?? */

                    return afficher(soustractionF(nb1,nb2));
                    
                break;

                case 'addition':

                    return afficher (additionF(nb1,nb2));    

                break;

                case 'division':

                    return afficher (divisionF(nb1,nb2));

                break;

                case 'multiplication':

                    return afficher (multiplicationF(nb1,nb2));

                break;
                
                
                default : 'ERREUR';
                break;
                
                    


              }}; 


              
            
            /* FONCTIONS UTILISEES */


            function soustractionF (nb1,nb2)
            {
                let resultat = nb1 - nb2;

                return resultat;
            }

            function additionF (nb1,nb2)
            {
                let resultat = nb1 + nb2;
                
                return resultat
            }

            function divisionF (nb1,nb2)
            {
                let resultat = nb1 / nb2;

                return resultat;
            }

            function multiplicationF (nb1, nb2)
            {
                let resultat = nb1 * nb2;

                return resultat;
            }

           


            function afficher (paramText)

            {

                document.write (paramText);
                document.write ('<br>');


            }

        

    </script>
    
</body>
</html>
 ````
 </details>
 
## (EXO 5) VITESSE LUMIERE

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


 
