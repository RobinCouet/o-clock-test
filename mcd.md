# MCD

Dans ton MCD, tu dis que un `USER` peut `LIKE` `1,1` `PRODUCT`, mais il peux en like entre 0 et l'infini (du moins autant que de produit existant sur le site, donc la relation sera effectivement du `many to many` mais en `0,N`, de même pour l'autre sens, un produit peut etre `LIKE` par 0 a l'infini `USER`, donc en `0,N` également

Un USER doit également avoir au minimum une adresse, donc la relation entre `USER` et `ADDRESS` sera `1,N` afin d'être sur qu'un `USER` ne puisse pas se retrouver sans `ADDRESS`

## Exemples d'outils

Afin de faire des MCD, tu peux utiliser différents outils tel que

 1. Merise, qui est une méthode de modélisation les plus utilisés
 2. PowerDesigner
 3. ER/Studio