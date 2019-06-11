# MODALS TUNNELS GFR


## **Description du projet**
Modals accès tunnels disponibles sur tout le site GFR et pouvant être appelées depuis n'importe quel élément HTML.  

Pour ouvrir une modal, il suffit d'avoir l'attibut sur la balise html `data-target="auto"`.  
La modal doit être présente sur la page et posséder l'attribut `data-modal="auto"`.  

### Fichiers
  * `index.html` : code html des modal avec des boutons de test pour ouvrir  
  * `modal.css` : styles des modal avec des styles spécifiques aux tunnels  
  * `modal.min.css` : css minifié *(à utiliser en prod)*  
  * `modal.min.js` : js minifié *(à utiliser en prod)*  

### Identifiants des modals
  * `auto` : Tunnel Auto  
  * `habitation` : Tunnel Habitation  
  * `sante` : Tunnel Santé & Prévoyance  
  * `tunnel-velo` : Tunnel Vélo  
  * `tunnel-contact` : Tunnel Contact  


---


## **Règles de gestion**


### Différents états du CTA

> **C'est le CSS qui gère les styles des différents 2 états.**

Tant que le champ input **Code postal** n'est pas renseigné et correct, l'attribut `disabled` doit être présent sur le bouton :  
```html
<button class="gfr-modal-cta" disabled>FAIRE UN DEVIS AUTO</button>
```

Lorsque le champ input **Code postal** est renseigné et correct, l'attribut `disabled` doit être retiré sur le bouton :  
```html
<button class="gfr-modal-cta">FAIRE UN DEVIS AUTO</button>
```


### Gestion des erreurs
Il suffit d'ajouter la classe `.gfr-modal-error` au bloc parent `.gfr-modal`.  
Cela fera apparaitre le message d'erreur, et mettra le champ input avec un contour rouge.  
Le CTA doit posséder l'attribut `disabled` afin de ne pas être cliquable.  

```html
<div data-modal="auto" class="gfr-modal gfr-modal-tunnel gfr-modal-error" style="display: none;">
...
	<button class="gfr-modal-cta" disabled>FAIRE UN DEVIS AUTO</button>
```


### Accélérateur
L'accélerateur doit se trouver dans le bloc `.gfr-modal-footer` et être encapsulé dans un bloc `.gfr-modal-tunnel-accelerateur`.  

  * Exemple **accélérateur contribué** :
```html
<div class="gfr-modal-footer">
  <div class="gfr-modal-tunnel-accelerateur">2 MOIS OFFERTS*</div>
</div>
```

  * Exemple **accélérateur non contribué** :
```html
<div class="gfr-modal-footer"></div>
```
> Le bloc `.gfr-modal-footer` doit être vide si l'accélérateur n'est pas contribué.  


---


## **Règles techniques**

  * Le code HTML des modals doit se trouver tout en bas de page, en dehors des sections du site (type `Header`, `Footer`, ...).  
	L'idéal serait juste sous le `Footer`.  

  * Ne pas utiliser les mêmes `id` dans les différentes modals. Les `id` HTML doivent être uniques !  

  * Utiliser les fichiers `css` et `js` minifiés.  
