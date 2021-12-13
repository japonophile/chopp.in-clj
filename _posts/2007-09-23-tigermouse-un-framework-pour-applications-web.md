---
layout: post
title: "Tigermouse, un framework pour applications web"
date: "2007-09-23"
type: post
published: true
status: publish
---

Cela fait quelques temps que je m'intéresse à la création d'**applications web**.

Parmi les plus connues aujourd'hui, il y a la "suite Google": gmail, google docs, google spreadsheets, et (lancée récemment) google presentations. De merveilleux exemples d'applications web, qui à la différence d'un simple site web offrent les fonctionnalités d'un logiciel avec un browser comme GUI. Techniquement, cela fait longtemps que les webapp auraient pu voir le jour, en utilisant la technologie des applets Java, mais plusieurs facteurs (selon moi, entre autre: le fait qu'il faille installer Java, la lourdeur des applets, etc) ont ralenti leur développement. Aujourd'hui, **AJAX** semble remédier à certains de ces problèmes, et permettra peut-être aux webapp de se multiplier. AJAX couplé à **Flash** pour les applications gourmandes en graphismes (p.ex. google maps ou geni.com), permet de faire autant si pas mieux que les applets, et fonctionne dans tout browser "moderne".

Bref, je voulais donc me lancer dans la programmation d'une webapp, et ai commencé à rechercher une technologie adaptée pour la partie **serveur**. Je vois au moins les choix suivants: **J2EE** (JSP, Servlets...), **PHP**, **ASP**... Quelles technologies les "grands" utilisent-ils? (Google, e-Bay, Amazon, YouTube, ...) J'ai lu ([ici](http://nerddawg.blogspot.com/2004/06/how-ebay-uses-j2ee-to-support-1.html "J2EE success (?) story")) qu'e-Bay serait passé à J2EE, mais que cela n'aurait pas vraiment été un succès... Et [ailleurs](http://www.javalobby.org/java/forums/m91833701.html "Is J2EE obsolete?"), la rumeur que google et amazon utiliseraient **LAMP** pour leurs gros serveurs... Si quelqu'un a des infos intéressantes dans ce domaine, je suis preneur.

J'ai commencé par explorer la piste PHP (qui me semblait plus "lightweight" pour commencer, que J2EE). Je cherchais un framework PHP qui me permettent d'implémenter une webapp de façon élégante; une bonne approche me semblait être le **MVC** (Model View Controller). Après quelques essais (j'ai exploré quelques frameworks listés [ici](http://www.phpwact.org/php/mvc_frameworks "PHP MVC frameworks")), je suis tombé sur [**Tigermouse**](http://tigermouse.epsi.pl/ "Tigermouse PHP/AJAX MVC framework"), qui m'a séduit par sa simplicité, et la "pureté" de son implémentation du MVC. Le code est extrêmement bien documenté, et répondait assez bien à mes attentes: en quelques lignes, on peut vraiment créer une webapp PHP/AJAX sans avoir à écrire une ligne de Javascript. Tigermouse me semble vraiment prometteur, même s'il manque encore de maturité pour l'instant.

Voilà le résultat de mes pérégrinations.  Pour les _geek_ qui ont suivi jusqu'ici, je serais content de lire vos réactions.
