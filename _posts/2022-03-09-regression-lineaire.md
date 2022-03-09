---
layout: post
title:  "La régression linéaire"
date:   2022-03-09
categories: data science geek PAR CHUGA
---

Aujourd'hui nous allons parler de régression linéaire, l'une des plus anciennes méthodes d'apprentissage statistique. Nous commençons donc volontairement par une piste verte pour s'échauffer et partir sur une base simple dont vous avez probablement tous déjà entendu parler dans votre cursus.

Dans cet article, nous aborderons dans un premier temps l'aspect théorique de la régression linéaire, avant de donner quelques exemples d'implémentation avec les outils les plus couramment utilisés.

## Théorie

L'idée de la régression linéaire est simple : il s'agit de faire l'approximation qu'entre un ensemble de données et un autre il existe une relation "linéaire", c'est-à-dire du type $y=ax+b$, qui peut être représentée par une droite (cf. figure ci-dessous).

![Exemple de régression linéaire](/assets/images/linear_regression_wikipedia.png)

Source : https://commons.wikimedia.org/wiki/File:Linear_regression.svg?uselang=frv

Pour ne pas rebuter les moins matheux d'entre vous, prenons d'emblée un exemple que l'on utilise quasi-quotidiennement en anesthésie-réanimation : le *poids idéal théorique*. Cette formule a été développé initialement en 1983 par J. Daniel Robinson et ses collègues pour adapter la posologie des molécules prescrites<sup>1</sup>. Elle se base sur une régression linéaire des tables de poids idéaux publiés par la compagnie d'assurance Metropolitan Life<sup>2</sup>.

![Régression linéaire donnant le poids idéal des femmes de stature intermédiaire<sup>1</sup>.](/assets/images/weight_height_medium_women_original_article_1983.png)

Régression linéaire donnant le poids idéal des femmes de stature intermédiaire<sup>1</sup>.

Les tables originales n'étant plus disponibles, nous utiliserons leur version actualisée de 1999 :

![](/assets/images/MetLife_1999_weight_height_women_table.png)

Après avoir converti les tailles en cm, les poids en kg, et en ne considérant que la taille médiane des femmes de stature intermédiaire, nous obtenons le tableau de valeurs suivant :

![](/assets/images/MetLife_1999_weight_height_medium_women_table_converted.png)

Ce qui graphiquement donne le résultat suivant :

![](/assets/images/weight_height_medium_women_MetLife_1999_graph.png)

On voit que la taille minimale est 157 cm, donc par exemple pour une femme de 150 cm on ne peut pas se référer à la table pour avoir une estimation du poids idéal. C'est là que la régression linéaire entre jeu : nous allons trouver la droite qui permet d'estimer au mieux ces points du graphique.

Pour cela, il s'agit de trouver les paramètres $a$ et $b$ qui minimisent l'erreur que l'on fait lorsqu'on fait l'approximation que le lien entre le poids $y$ et la taille $x$ s'écrit de la forme $y=ax+b$. Dans notre exemple, si l'on choisit $a = 0.5$ et $b = -18$, on obtient les valeurs suivantes :

![](/assets/images/example_linear_approximation_MetLife_table.png)

Ce qui donne graphiquement la courbe rouge ci-dessous :

![](/assets/images/example_linear_approximation_MetLife_graph.png)

Ceci semble être une approximation convenable, mais on ne sait pas si c'est la "meilleure", c'est-à-dire minimisant l'erreur de mesure. Plusieurs méthodes existent, mais la plus connue et la plus utilisée dans ce contexte reste la [méthode des moindres carrés](https://fr.wikipedia.org/wiki/M%C3%A9thode_des_moindres_carr%C3%A9s). Sans rentrer dans les détails mathématiques ici, cette méthode permet de calculer exactement la solution qui minimise l'[erreur quadratique](https://fr.wikipedia.org/wiki/Erreur_quadratique_moyenne). Toujours dans le contexte de notre exemple, si l'on fait la différence entre les points bleus et la courbe rouge, nous obtenons les valeurs de l'avant-dernière colonne du tableau suivant :

![](/assets/images/example_linear_approximation_MetLife_mean_square_error_table.png)

Les valeurs de la dernière colonne ne sont autre que celles de l'avant-dernière colonne mises au carré (d'où le nom de quadratique). La somme de cette dernière colonne est ce qu'on appelle l'erreur quadratique et s'élève ici à 16,51. En utilisant la méthode des moindres carrés, on trouve que les valeurs optimales sont environ $a = 0.54$ et $b = -25.6$. Ceci donne les valeurs suivantes :

![](/assets/images/linear_regression_MetLife_table.png)

On constate que la valeur de l'erreur quadratique est plus faible qu'avec nos valeurs initiales, ici 4,60. On peut également constater que la droite épouse mieux les valeurs graphiquement :

![](/assets/images/linear_regression_MetLife_graph.png)


## Implémentation

### Tableurs

- Excel
- Google sheets
- Open Office

### Langages de programmation

- R
- Python

## Sources

1.  Robinson JD, Lupkiewicz SM, Palenik L, Lopez LM, Ariet M. Determination of ideal body weight for drug dosage calculations. *Am J Hosp Pharm.* 1983 Jun;40(6):1016-9. PMID: 6869387.
2.  Metropolitan Life Insurance Company. Desirable weight in indoor clothing. *Statistical bulletin* no. 40.1959 Nov-Dec.