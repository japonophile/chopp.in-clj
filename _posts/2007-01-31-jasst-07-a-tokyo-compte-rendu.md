---
layout: post
title: "JaSST '07 à Tokyo: compte rendu"
date: "2007-01-31"
type: post
published: true
status: publish
---

Hier et aujourd'hui, j'ai participé au JaSST '07 à Tokyo (Japan Symposium on Software Testing in Tokyo) qui eu lieu dans le prestigieux hôtel de "Meguro-Gajoen" (目黒雅叙園). Voici donc un bref compte rendu.

**Jour 1 (mardi, 30 janvier 2007):**

La plus grande partie de la journée fut consacrée à l'exposé d'Edward Yourdon, qui consista essentiellement en un résumé de son: "**Death March**: how to survive mission impossible projects". Le matin, pour le speech principal du Symposium, Yourdon présenta les chapitres 1 à 3 du livre:

- Qu'est-ce qu'un projet "marche de la mort", et pourquoi diable se lance-t-ton dans une telle aventure? Son message est que la plupart des projets de développement logiciel sont essentiellement des "death march" (càd des projets dont certaines contraintes telles la durée, les effectifs, le budget, les fonctionalités requises, dépassent de plus de 50% les contraintes d'un projet "normal")...
- Le problème numéro 1 des "death march": la politique. Autrement dit, ce qui cause le plus souvent l'échec d'un projet de développement logiciel sont les incessantes batailles politiques entre management, clients, et autres acteurs.
- Le second majeur problème est celui des négociations: souvent un projet se transforme en "marche de la mort" lorsque le chef de projet échoue dans les négociations de compromis entre différentes composantes (durée, coût, resources, etc.).

L'après-midi, j'ai choisi d'entendre la suite de l'exposé d'Edward Yourdon (il s'agissait d'une session spéciale payante, mais puisque mon boss m'a permis d'y participer...). Il a présenté les chapitres 4 à 6 (et un peu du reste) de son livre:

- Autre problème important d'un projet du type "death march": les facteurs humains, ou selon le terme américain "peopleware". Yourdon a d'ailleurs mentionné à maintes reprises le livre "Peopleware" de ses amis Tom DeMarco et Tim Lister. Obtenir le droit de se constituer une équipe valable et travailler le "team building" semblent être des facteurs importants dans la réussite d'un projet "death march".
- Yourdon a également évoqué les méthodes et outils ("processes and tools") utilisés au cours du projet, tout en rappelant que ce facteur était sans doute moins déterminant pour la réussite ou l'échec du projet que les composantes évoquées plus haut.
- Enfin,si je me rappelle bien, il a parlé brièvement d'autres aspects comme la planification (selon une méthode appelée "critical chain"), le controle et monitoring du projet, avant d'aborder la "dynamique des processus" (un concept que je n'ai pas bien compris).

Mon appréciation globale des exposés de Yourdon est plutôt positive, avec un bémol cependant: j'ai regretté qu'il se contente de nous présenter le contenu de son livre (car le livre, chacun peut le lire par soi-même), sans entre davantage dans le thème du symposium: le test software. Ceci dit, le contenu du livre (que j'ai acheté il y a deux semaines sur Amazon, et que je me suis fait dédicacer par Yourdon --yey!) est très interessant, et le fait d'entendre le contenu du livre expliquè par l'auteur en personne est quand même une chance à ne pas manquer.

Enfin, pour terminer cette première journée, j'ai assisté à une session sur un sujet tout autre, le "**model-based testing**". L'idée est la suivante: supposant l'existence d'un modèle (UML par exemple) d'un logiciel, il doit théoriquement être possible de générer automatiquement des tests sur base de ce modèle, de les exécuter (toujours automatiquement) et de vérifier les résultats, tout cela sans effort. Très belle théorie, mais qui m'avait l'air un peu fumeuse. Autant la génération automatique de code (au moyen de CASE tools) ne semble pas être une réussite globale, autant j'ai de sérieux doutes sur les chances de telles entreprises. Mais bon, chez Hitachi, ils payent apparemment un gars (au moins, celui qui a donné l'exposé) pour faire de la recherche dans ce domaine...

**Jour 2 (mercredi 31 janvier 2007):**

La première session de la journée était plutôt basique et concrète. Il s'agissait d'une sorte de saynette mettant en scène un jeune programmeur inexpérimenté, confronté à des problèmes concrets de test, qui **demande conseil à trois "sages"**, des testeurs professionels expérimentés qui lui donnent des conseils pratiques.

Les trois "sages" étaient:

- Toru Matsuodani ([Debug Engineering Institute](http://www.debugeng.com/))
- Koichi Akiyama ([Fuji Xerox](http://www.fujixerox.co.jp/))
- Mikio Suzuki ([TIS](http://www.tis.com/))

Le "jeune programmeur" leur a soumis deux problèmes, l'un concernant le test d'un tableau de bord (logiciel embarqué), et l'autre un système de vente de tickets par internet (type "entreprise"), et chacun des trois "sages" proposait une approche concrète pour tester le système en question. Suzuki était partisan de l'approche basique de "table décisionnelle" (Decision Table, DT). Akiyama partait d'un diagramme causes-effets (Cause Effect Graph, CED) mais pour construire également une table décisionnelle (réduite). Et Matsuodani lui, proposait l'approche du "diagrame de flux de causes" (Cause Flow Diagram, CFD), qui ne me rappelait rien de connu (une approche plutôt visuelle, ne me semblant pas adaptée à des problème de taille réelle).

C'était un exposé très concret et pratique, qui m'a fait prendre conscience de l'importance de revenir à la théorie pour l'appliquer dans les problèmes que je rencontre tous les jours. L'importance aussi de bien vérifier la couverture des test ("test coverage"), pas seulement des spécifications de cas nominaux, mais aussi des comportement interdits, et de la masse de comportements non couverts dans les spécifications.

La seconde session était donnée par un représentant de la firme [Mercury](http://www.mercury.com/jp/) (récemment acquise par [HP](http://welcome.hp.com/country/jp/ja/welcome.html)), qui nous a parlé de l'importance d'une **vision globale des activité****s de test** en regard avec le cycle de développement. Depuis la définition des spécifications jusqu'aux tests d'acceptance, l'importance de planifier les tests, d'en garder la trace, de les documenter, de les monitorer, etc. Tout cela pour en arriver à la présentation de leur outil "Test Director for QC". Un outil permettant de gérer les spécifications, de créer des cas de test, de vérifier la couverture des spécifications par les tests, d'exécuter les tests automatiquement (via un language de controle de GUI), d'enregistrer les résultats, ainsi que les problèmes survenus lors des tests. Tout ça m'avait l'air très intéressant, mis à part le fait que cela implique une dépendance totale à leur outil. Tout est intégré, mais que faire si je souhaite utiliser DOORS pour gérer mes spécifications, ou encore gérer mes bugs via Bugzilla plutôt que via leur truc?

L'après-midi, Toru Matsuodani (Debug Engineering Institute) nous parla de sa "**Vision future dans le domaine du test logiciel**". Dans la pratique, on observe que tout projet software coûte 30% en développement, et 70% en test. Comment réduire le coût (relatif) du test? Selon Matsuodani, on a pendant un temps cru que l'approche visant simplement à améliorer les mèthodologies de développement (CMM, et autres) seraient suffisantes, mais apparemment cela ne change pas le coût relatif de 70% pour les tests. La raison selon lui, est que ce n'est pas en améliorant la qualitè du logiciel produit que l'on rèduira l'effort nécessaire pour le tester. En effet, l'effort de test est lié à la taille de l'espace des entrées-sorties du système, càd l'espace que les testeurs devront parcourir pour trouver les bugs. Qu'il y ait moins de bugs ne réduit pas cet espace, mais c'est en réduisant la complexité du système (p.ex en divisant le logiciel en plus petits composants) que l'on pourra réduire l'espace à parcourir lors des tests. Et cela n'est réalisable, selon lui, qu'en passant d'un design du type "facile à fabriquer" à un design du type "facile à tester". Autrement dit, prendre en compte le problème du test dès la conception du logiciel.

Cela nous mène déjà à la dernière session de ce symposium: une table ronde mettant en scène les orateurs suivants:

- Edward Yourdon (NODRUOY Inc.)
- Yamaura (Tokai University)
- Toru Matsuodani (Debug Engineering Institute)

Le thème du débat était "**Taming a Monster**", càd: "Dresser un monstre", faisant allusion au "monstre des bugs" auquel s'attaque l'équipe de testeurs corps et âme. Chaque orateur avait préparé un court exposè, présentant sa façon d'aborder le problème.

Matsuodani dans son exposé très imagé, pointa l'importance de: (1) réduire les attentes des clients, du management etc; (2) augmenter la motivation de l'équipe de test/développement; et (3) réduire la complexité du logiciel à tester en "divisant pour régner".

Yamaura, lui, parla de l'importance des compromis dans la négociation des spécifications, du "triage", de l'importance de faire comprendre au management que le coût du software en fonction des resources ne répond pas à une loi linéaire (cf loi de Putnam), et proposa d'assigner une personne seulement responsable de vérifier la couverture suffisante des tests entrepris, ainsi qu'un "gardien des spécifications".

Enfin, Yourdon mentionna une fois de plus les problèmes politiques, l'importance de la collaboration (au sein de l'équipe et en dehors), et de la négociation de compromis, rejoignant donc l'exposé de Yamaura.

Le temps de questions-réponses fut intéressant également. On y aborda notamment les points suivants: le fait que très peu de CTO (ou CIO) deviennent CEO montre que les priorités des entreprises de nos jours sont davantages dans la finance que la technologie. Egalement, l'importance de s'intéresser au phénomène "open-source", mentionnant notamment Linux et Wikipedia.

**Conclusion**

Je ne vais plus la faire longue, juste dire que j'ai trouvé ce symposium très intéressant. Dépassant largement la discussion du test logiciel, il m'a donné envie de me plonger dans d'autres bouquins pour approfondir un tas de concepts nouveaux.
