# Algo_revision


Déterminer si la string passée en parametre d'une fonction est un palindrome.
 ex de palindrome : kayak, ressasser, sos, lol, racecar.
 
 => BONUS : Les caractères spéciaux, chiffres, espaces, majuscules devront être supprimés.
 
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


 
 
