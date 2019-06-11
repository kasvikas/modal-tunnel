# BLOC IMMERSIF GFR


## **Description du projet**
Bloc immersif responsive, avec une possiblité de le personnaliser sur mobile uniquement.  
Test visible sur : https://groupama.vikas.fr/immersive/  

### Fichiers
  * `index.html` : code html du bloc immersif  
  * `immersive.css` : styles  
  * `immersive.min.css` : css minifié *(à utiliser en prod)*  
  * `backend.html` : code html du back-end contribution  

### Back-end contribution
La partie contribution du back-end a également été concue avec les UX et les contributeurs afin d'être au plus près des besoins.  
Reprendre les intitulés iso (majuscules, parenthèses, etc…) ainsi que l'ordre des champs.  
Modèle du Back-end : https://groupama.vikas.fr/immersive/backend.html  


---


## **Règles de gestion**
Le bloc à intégrer est la div `.g-immersive`.  


### Image de fond
Il suffit de rajouter un attribut style qui définit la règle `background-image` :  
```html
<div class="g-immersive" style="background-image: url('https://www.groupama.fr/chemin/vers/image.jpg');">
```
Les tailles recommandées pour l'image de fond sont les suivantes :   
  * Desktop : 1440x480
  * Mobile : 720x720


### Position du texte
La position du texte est pilotée depuis le parent `.g-immersive`.  
Par défaut celle-ci est centrée en hauteur.  
  * Si l'option `Haut` est sélectionnée, on ajoute la classe suivante : 
```html
<div class="g-immersive g-immersive--top">
```
  * Si l'option `Bas` est sélectionnée, on ajoute la classe suivante : 
```html
<div class="g-immersive g-immersive--bottom">
```

### Couleurs par univers
Le code CSS contient directement les couleurs des univers.  
Par défaut, le vert Groupama sera appliqué.  
Les couleurs sont aussi pilotées depuis le parent `.g-immersive`.  

Par exemple pour l'auto, on ajoute la classe suivante :  
```html
<div class="g-immersive g-immersive--auto">
```
Voici les classes disponibles dans le CSS :  
  * Auto :        `.g-immersive--auto`
  * Habitation :  `.g-immersive--habitation`
  * Santé :       `.g-immersive--sante`
  * Prévoyance :  `.g-immersive--prevoyance`
  * Epargne :     `.g-immersive--epargne`
  * Banque :      `.g-immersive--banque`
  * Agri :        `.g-immersive--agri`
  * Pro :         `.g-immersive--pro`


### Couleurs personnalisées
Le back-end permet de sélectionner une couleur personnalisée via un code hexadécimal ou rgb.  
Celle-ci devra être appliquée à 2 endroits via un attribut style :  

  * à l'élément `.g-immersive__title` il sera appliqué la règle `color` :
```html
<h1 class="g-immersive__title" style="color: #ff0000;">
```
  * à l'élément `.g-immersive__subtitle-content` il sera appliqué les règles `background-color` et `box-shadow` :
```html
<h2 class="g-immersive__subtitle">
  <span class="g-immersive__subtitle-content" style="background-color: rgba(255, 0, 0, 0.8); box-shadow: 16px 0 0 rgba(255, 0, 0, 0.8), -16px 0 0 rgba(255, 0, 0, 0.8);">
```
> **IMPORTANT : il faudra transcoder la couleur en `rgba` et lui appliquer une transparence de 0.8, et bien reprendre les valeurs ci-dessus du box-shadow !**


### Type Hn du Titre et du Sous-titre
Par défaut, les titres et sous-titres doivent être des balises `<p>`.


### Sous-titres
Les sous-titres ont été découpés en 3 lignes pour faciliter la contribution.  
Les balises `<br>` doivent se trouver au début des lignes 2 et 3, si elles sont contribuées.  

Exemple avec 2 lignes contribuées :
```html
<h2 class="g-immersive__subtitle">
  <span class="g-immersive__subtitle-content">
    Ligne 1
    <br> Ligne 2
  </span>
</h2>
```


### Ajouter flèche au bouton CTA
L'ajout d'une flèche au CTA est pilotée depuis le parent `.g-immersive`.  
  * Si l'option `Ajouter une flèche au bouton CTA` est cochée, on ajoute la classe suivante : 
```html
<div class="g-immersive g-immersive--cta-fleche">
```


### Liens
3 types d'actions peuvent être ajoutées au visuel :  
  * Lien interne  
  * Lien externe  
  * Ouverture d'une modal d'entrée tunnel  
> **IMPORTANT : si les 3 types de liens sont contribués, il faut respecter la priorité : MODAL (n°1), LIEN EXTERNE (n°2), LIEN INTERNE (n°3)**

**Pour ajouter un lien**, il suffit d'ajouter au parent `.g-immersive` :
```html
<div class="g-immersive" onclick="window.open('https://www.google.fr','_self')">
```
> Si l'option `Ouvrir le lien dans un nouvel onglet` a été sélectionnée, remplacer `_self` par `_blank`

**Pour ajouter l'ouverture d'une modal**, il suffit d'ajouter au parent `.g-immersive` :
```html
<div class="g-immersive" data-target="auto">
```


### Marge bas
Il suffit de rajouter au style du parent `.g-immersive` la règle `margin-bottom` :  
```html
<div class="g-immersive" style="margin-bottom: -32px;">
```
> **C'est le CSS qui se charge de remettre la valeur à 0 sur tablette et mobile.**


### Contribution Mobile
**Seuls ces champs sont contribuables sur mobile :**  
  * Image mobile (720x720)
  * TITRE mobile
  * SOUS-TITRE - ligne 1
  * SOUS-TITRE - ligne 2
  * SOUS-TITRE - ligne 3
  * Libellé bouton CTA
  * Ajouter une flèche au bouton CTA

> **Du moment où une des valeurs est contribuée sur mobile, cela écrase tous les champs respectifs sur desktop.**  
> **Il faut donc toutes les contribuer.**  
> **Si rien n'est contribué, les valeurs du desktop s'appliquent.**  
