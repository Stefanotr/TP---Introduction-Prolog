# TP : Introduction à la Programmation Logique avec Prolog

Ce dépôt contient le code source et les réponses aux exercices du TP d'introduction à Prolog. L'objectif est de manipuler les concepts de faits, de règles, de récursion et de gestion de listes.

## 🛠 Installation et Utilisation

1. Installez **SWI-Prolog** ou utilisez [SWISH](https://swish.swi-prolog.org/).
2. Chargez le fichier `tp.pl` dans l'interpréteur :
```prolog
?- [tp].

```



---

## 📝 Réponses aux Exercices

### Partie 1 : Faits et Requêtes

Voici les requêtes correspondant aux questions de l'exercice 1 :

* **Qui est rouge ?** : `?- couleur(X, rouge).`
* **Qu’est-ce que mange Léa ?** : `?- mange(lea, X).`
* **Qui mange une pomme ?** : `?- mange(X, pomme).`
* **Quel objet est de couleur jaune ?** : `?- couleur(X, jaune).`

### Partie 2 : Règles complexes

Les règles `aime_fruit/1`, `meme_couleur/2` et `aiment_la_meme_chose/2` ont été ajoutées pour lier les faits de consommation aux propriétés des objets (couleurs et types).

### Partie 3 : Manipulation des listes

#### Exercice 3 : Longueur d'une liste

**Question : Expliquer en 2 phrases le fonctionnement de la règle `longueur`.**

> La règle fonctionne par récursion : elle décompose la liste jusqu'à atteindre la liste vide (cas de base valant 0). En remontant la pile d'appels, elle ajoute 1 pour chaque élément retiré, calculant ainsi le total.

**Question : Pourquoi `_` dans la tête de la règle ?**

> Le symbole `_` est une variable anonyme utilisée ici car la valeur de l'élément de tête n'importe pas pour le calcul de la longueur ; seule sa présence compte pour incrémenter le compteur.

#### Exercice 4 : Somme d'une liste

La règle `somme(Liste, Résultat)` a été implémentée de manière récursive avec un cas de base pour la liste vide `somme([], 0)`.

### Partie 4 : Relations familiales

Mise en place d'une base de données généalogique.

* **Ancêtre** : Implémenté de façon récursive pour gérer toutes les générations.
* **Frère ou Sœur** : Vérifie que les individus partagent un parent et sont des entités distinctes (`A \= B`).

**Requêtes de test :**

```prolog
?- grand_parent(sara, luc). % Retourne true
?- ancetre(andre, luc).     % Retourne true

```

### Partie 5 : Problèmes logiques

* **Membre** : Recherche si un élément appartient à la tête ou à la queue de la liste.
* **Maximum** : Utilisation de la structure `(Condition -> Then ; Else)` pour comparer les éléments successivement lors de la remontée récursive.

---

## 📂 Structure du fichier `tp.pl`

Le fichier contient l'intégralité du code dans cet ordre :

1. **Base de faits** (couleurs, consommations, types).
2. **Règles de préférences** (`aime`, `aime_fruit`, etc.).
3. **Outils de listes** (longueur, somme).
4. **Base familiale** (hommes, femmes, parents) et règles de parenté.
5. **Algorithmes logiques** (membre, maximum).

---

### Tests rapides

Pour vérifier le bon fonctionnement global, vous pouvez copier-coller ces requêtes :

```prolog
% Test Somme
?- somme([10, 20, 30], 60).
% Test Maximum
?- max_liste([1, 5, 3], 5).
% Test Famille
?- frere_ou_soeur(luc, X).

```