# PRD — Analyseur d'avis Google pour boulanger indépendant

## Problème

Le boulanger indépendant consulte ses avis Google un par un depuis son téléphone, sans jamais avoir de vue d'ensemble. Il ne sait pas si sa note progresse ou se dégrade sur la durée, et il n'a aucun moyen de détecter rapidement une mauvaise période. Cette absence de lisibilité le prive d'un levier simple pour piloter la qualité perçue de sa boutique. Le déclencheur est souvent une prise de conscience brutale — une série d'avis négatifs ou un concurrent mieux noté — qui révèle le manque d'outil adapté à son niveau de disponibilité et de technicité.

## Solution

L'outil permet au boulanger de charger l'export de son profil Google Business et d'obtenir immédiatement une vue de sa note actuelle et de son évolution dans le temps. Pas de configuration, pas d'apprentissage : une seule action, un seul écran, des indicateurs lisibles en un coup d'œil.

## Utilisateur cible

Boulanger propriétaire d'une boutique indépendante, peu à l'aise avec les outils numériques complexes. Il consulte l'outil seul, depuis son téléphone ou sa tablette, en fin de journée entre deux fournées. Il n'a ni le temps ni l'envie de naviguer dans des tableaux de bord élaborés — il veut une réponse rapide à une question simple : est-ce que mes clients sont plus ou moins satisfaits qu'avant ?

## User Stories

**US-1** — En tant que boulanger, je veux charger mon fichier export ZIP depuis mon navigateur, afin de lancer l'analyse de mes avis sans installation.

**US-2** — En tant que boulanger, je veux voir ma note moyenne actuelle affichée clairement, afin de savoir en un instant où j'en suis.

**US-3** — En tant que boulanger, je veux voir l'évolution mensuelle de ma note sur tout mon historique, afin de savoir si je progresse ou si je décroche.

**US-4** — En tant que boulanger, je veux accéder à l'outil depuis mon téléphone ou mon ordinateur sans rien installer, afin de le consulter quand je veux.

**US-5** — En tant que boulanger, je veux voir un message d'erreur clair si mon fichier est invalide ou vide, afin de comprendre ce qui s'est passé et ne pas rester face à un écran blanc.

## Critères de succès

1. La note moyenne s'affiche en moins de 5 secondes après le chargement du fichier ZIP.
2. Un graphe d'évolution mensuelle est visible sur tout l'historique contenu dans le fichier.
3. Si le fichier est vide ou mal formé, un message d'erreur explicite s'affiche à la place des indicateurs.

## Hors périmètre

- Analyse des thèmes ou mots-clés contenus dans le texte des avis.
- Suivi du taux de réponse aux avis et du délai moyen de réponse.
- Comparaison avec d'autres établissements ou concurrents.
- Notifications ou alertes automatiques.
- Récupération automatique des avis Google sans action de l'utilisateur.
- Export ou génération de rapport PDF.

## Décisions d'implémentation

- L'outil fonctionne depuis un navigateur web, sans installation, sur mobile et sur desktop.
- L'utilisateur charge un fichier ZIP issu de l'export Google Takeout de son profil Google Business — c'est la seule action requise.
- Le graphe d'évolution est en granularité mensuelle et couvre tout l'historique présent dans le fichier, sans filtre à configurer.
- L'interface ne demande aucun paramétrage : l'utilisateur charge le fichier, les indicateurs s'affichent.
- En cas de fichier vide ou non reconnu, un message d'erreur clair remplace l'affichage des indicateurs.

## Notes complémentaires

La récupération automatique des avis Google (sans passer par un export manuel) est identifiée comme évolution future, hors périmètre de cette version. L'outil repose sur le format ZIP produit par Google Takeout — toute modification de ce format par Google constitue une dépendance externe à surveiller.
