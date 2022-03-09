---
layout: post
title:  "La régression linéaire"
date:   2022-03-09
categories: data science geek PAR CHUGA
---

Aujourd'hui nous allons parler de régression linéaire, l'une des plus anciennes méthodes d'apprentissage statistique. Nous commençons donc volontairement par une piste verte pour s'échauffer et partir sur une base simple dont vous avez probablement tous déjà entendu parler dans votre cursus.

Dans cet article, nous aborderons dans un premier temps l'aspect théorique de la régression linéaire, avant de donner quelques illustrations dans la littérature médicale récente et nous conclurons par des exemples d'implémentation avec les outils les plus couramment utilisés.

## Théorie

L'idée de la régression linéaire est simple : il s'agit de faire l'approximation qu'entre un ensemble de données et un autre il existe une relation "linéaire", c'est-à-dire du type $y=ax+b$, qui peut être représentée par une droite (cf. figure ci-dessous).

![Exemple de régression linéaire](/assets/images/linear_regression_wikipedia.png)