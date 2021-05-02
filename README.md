# Algo_revision


Déterminer si la string passée en parametre d'une fonction est un palindrome.
 ex de palindrome : kayak, ressasser, sos, lol, racecar.
 
 => BONUS : Les caractères spéciaux, chiffres, espaces, majuscules devront être supprimés.
 
 ```js
 
 

var tab = [];
var tab_2 = [];


function palindrome(str) {

str = str.replace(/[^0-9a-zA-Z.,''""" "]/gi, '')
for (let i = 0; i < str.length; i++)
  {
  tab.push(str[i]);
  
  }
for (let i = str.length-1; i >= 0; i--)
  {
  tab_2.push(str[i]);
  
  }

  

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


 
 
