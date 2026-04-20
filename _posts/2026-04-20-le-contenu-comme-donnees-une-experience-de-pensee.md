---
layout: post
title: "Le contenu comme données : une expérimentation"
category: Billets
excerpt_separator: <!--more-->
tag: Blogue
lang: FR
ref: content-as-data
---

On se bute constamment au même problème avec le contenu des programmes et services du gouvernement du Canada : une règle ou un montant change dans un programme, et cinq équipes se précipitent pour mettre à jour cinq choses différentes. Une page Web, un PDF, un script de centre d'appels, un outil interne, un agent conversationnel, etc. J'ai donc passé quelques soirées à bâtir une preuve de concept pour voir à quoi ça ressemblerait si les règles ne vivaient qu'à un seul endroit.

<!--more-->

L'expérience porte sur 3 programmes du gouvernement du Canada : l'Allocation canadienne pour enfants, l'assurance-emploi et la Sécurité de la vieillesse. Chaque programme est encodé dans un seul fichier JSON contenant tous les seuils, taux, tranches de réduction et exemples, en anglais et en français. Puis j'ai construit plusieurs outils à partir de cette même « source unique de vérité ».

Jetez un coup d'œil : [Expérience « API des règles GC (en anglais seulement) »](https://www.davidpepin.ca/gc-rules-api/webapp/)

<img class="img-fluid" style="border: 1px solid #ddd; border-radius: 4px; box-shadow: 0 2px 8px rgba(0,0,0,0.1);" src="{{ site.baseurl }}/images/web_app_api.png" alt="Page web donnant accès à plusieurs outiles bâtis avec les mêmes fichiers JSON."/>

## Plusieurs outils, une seule source

L'idée était de voir si une approche de type « Rules as code » appliquée à l'information clé des programmes pouvait alimenter différents outils. Voici ce que ça donne.

- Un [estimateur interactif](https://www.davidpepin.ca/gc-rules-api/webapp/estimator.html) où vous entrez votre situation et obtenez un montant calculé
- Du [contenu Web statique dans le style Canada.ca](https://www.davidpepin.ca/gc-rules-api/site/_site/en/canada-child-benefit/how-much.html), généré à partir du fichier JSON
- Un agent conversationnel local qui lit des fichiers Markdown générés à partir du JSON, réduisant les hallucinations
- Un [éditeur JSON](https://www.davidpepin.ca/gc-rules-api/webapp/editor.html) qui permettrait à un analyste de politiques de modifier les paramètres — seuils de revenu, taux de prestations, limites d'âge — sans jamais ouvrir un fichier JSON
- Un [explorateur d'API](https://www.davidpepin.ca/gc-rules-api/webapp/api.html), simulant comment n'importe qui pourrait interroger l'information des programmes par le biais d'une API

Sous le capot, les mêmes fichiers JSON.

On pourrait aller plus loin : des applications sécurisées, des scripts de centres d'appels, du matériel de formation, etc. Tout cela pourrait en théorie découler d'une source unique de vérité.

## Beaucoup à explorer

Je tiens à être clair : c'est une expérience, loin d'être prête à voir le jour. Les vrais programmes sont bien plus complexes que ce que couvrent ces fichiers JSON. La discrétion, les cas limites, les appels, les exceptions propres à certaines provinces — encoder tout cela relève autant de la gouvernance et des politiques que de la technologie. Je n'ai résolu aucun de ces problèmes avec cette expérience.

Ce que j'ai fait, par contre, c'est rendre l'idée suffisamment tangible pour commencer à expérimenter.

Peut-on imaginer un monde où du contenu gouvernemental précis sur les programmes et services serait offert à tous et à tous les outils, par le biais d'une API?

Le [dépôt est public sur GitHub](https://github.com/quidampepin/gc-rules-api). Explorez, fouillez. Dites-moi ce que vous trouvez.

*Bâti avec l'aide de Claude (Anthropic) pour le code et l'itération. Inspiré par [OpenFisca](https://openfisca.org/), le rapport [Better Rules](https://www.digital.govt.nz/showcase/better-rules-for-government-discovery-report/) de la Nouvelle-Zélande, et des conversations avec des collègues travaillant en prestation de services numériques au GC.*
