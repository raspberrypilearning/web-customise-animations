Chacune des animations de démarrage dans le fichier `animation.css` a un groupe de propriétés `animation` qui indique comment l'animation doit s'exécuter :

## --- code ---

language: html
filename: animation.css
line_numbers: true
line_number_start: 1
line_highlights: 2
-------------------------------------------------------

.spinme {
animation: rotate-center linear 8s 2; /\* Durée de l'animation et nombre de répétitions \*/
display: inline-block;
}

\--- /code ---

La ligne `animation` de l'exemple `spinme` est décomposée en :

- `rotate-center` : le nom de l'animation
- `linear`: le timing de l'animation (linéaire est la même vitesse de lecture tout au long de l'animation, d'autres exemples sont `ease`, `ease-in`, et `ease-out`)
- `8s`: la durée de l'animation en secondes
- `2`: le nombre de fois que l'animation doit être exécutée (peut être `infinite` pour une exécution continue)

Change l'une de ces valeurs pour modifier l'animation. Une autre façon de personnaliser l'animation est d'ajuster la règle `@keyframes`.  `@keyframes` contrôle l'apparence de l'élément lorsqu'un pourcentage de l'animation en cours est terminé.

Dans l'animation `rotate-center` utilisée par `spinme`, l'animation fait tourner l'objet de 0 degrés au début de l'animation (`0%`), à 360 degrés à la fin de l'animation (`100%`).

## --- code ---

language: html
filename: animation.css
line_numbers: true
line_number_start: 6
------------------------------------------------------------------------------

@keyframes rotate-center {
/\* Le code de l'animation spin me _/
0% { /_ Rotation de 0 à 360 degrés \*/
transform: rotate(0);
}
100% {
transform: rotate(360deg);
}
}

\--- /code ---

Des styles spécifiques peuvent être appliqués aux animations à d'autres points de pourcentage au cours de l'exécution de l'animation. Par exemple, l'animation `scale` a des points spécifiés à 0%, 20%, 40%, 60% et 80%.

## --- code ---

language: html
filename: animation.css
line_numbers: true
line_number_start: 6
------------------------------------------------------------------------------

@keyframes scale {
/\* Le code de l'animation d'échelle \*/
0% {
transform: scale(1, 1);
}
20% {
transform: scale(1.1, 1.1);
}
40% {
transform: scale(1.2, 1.2);
}
60% {
transform: scale(1.1, 1.1);
}
80% {
transform: scale(1, 1);
}
}

\--- /code ---

L'animation peut avoir plus d'un style modifié à chaque point. Par exemple, l'animation `bounce` modifie la taille et la coordonnée y pour créer un effet de rebond réaliste.

## --- code ---

language: html
filename: animation.css
line_numbers: true
line_number_start: 22
-------------------------------------------------------------------------------

@keyframes bounce {
/\* Le code de l'animation du rebond _/
0% {
transform: scale(1, 1) translateY(0); /_ Position de départ et taille réelle _/
}
10% {
transform: scale(1.1, 0.9) translateY(0); /_ Augmentation de la largeur et réduction de la hauteur pour un effet d'écrasement avant le rebond _/
}
30% {
transform: scale(1, 1) translateY(-6rem); /_ Retour à la taille réelle et déplacement de l'emoji de 100px vers le haut à partir de la position actuelle _/
}
50% {
transform: scale(1, 1) translateY(0); /_ Ramener l'emoji à sa position de départ \*/
}
}

\--- /code ---

Tu peux changer la couleur, la position, la taille, la rotation et bien d'autres propriétés si tu modifies le code `@keyframes`.
