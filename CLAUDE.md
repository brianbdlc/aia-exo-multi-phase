# Analyseur d'avis Google

## Stack
Client-side only — `index.html` + JSZip + Chart.js depuis CDN, aucun build, aucun serveur.
## Documents projet
Toujours lire ces documents avant de coder :
- @docs/PRD.md — pourquoi et quoi du produit
- @docs/PLAN.md — phases d'implémentation et user stories
- @docs/DESIGN.md — système design et direction visuelle
## Système design
Toujours lire DESIGN.md avant toute décision visuelle ou UI.
Polices, couleurs, espacements et direction esthétique y sont définis.
Ne pas dévier sans validation explicite.
En mode QA, signaler tout code qui ne respecte pas DESIGN.md.
## Conventions
- Fraunces **exclusivement** sur le chiffre de note central — pas sur les titres ni labels.
- `#D4762A` (ambré) uniquement sur la note, les étoiles, le graphe, les boutons primaires — rare = signifiant.
- ZIP parsé côté client ; aucune requête réseau après le chargement initial de la page.
- Modèle de donnée : `{ rating: number, date: string (ISO) }` — ne rien ajouter sans nécessité explicite.
- Phases 1→2→3 : rendu mocké (P1), données réelles (P2), gestion d'erreurs (P3) — ne pas mélanger.
## Jargon métier
- **Google Takeout** — export ZIP Google contenant les données du profil Google Business.
- **Avis / note** — évaluation étoilée (1–5) laissée sur Google Business.
- **Boulanger indépendant** — utilisateur cible : non-technicien, mobile-first, zéro tolérance pour la complexité.

#convention
 Analyseur d'avis Google

## Stack
Client-side only — `index.html` + JSZip + Chart.js depuis CDN, aucun build, aucun serveur.
## Documents projet
Toujours lire ces documents avant de coder :
- @docs/PRD.md — pourquoi et quoi du produit
- @docs/PLAN.md — phases d'implémentation et user stories
- @docs/DESIGN.md — système design et direction visuelle
## Système design
Toujours lire DESIGN.md avant toute décision visuelle ou UI.
Polices, couleurs, espacements et direction esthétique y sont définis.
Ne pas dévier sans validation explicite.
En mode QA, signaler tout code qui ne respecte pas DESIGN.md.
## Conventions
- Fraunces **exclusivement** sur le chiffre de note central — pas sur les titres ni labels.
- `#D4762A` (ambré) uniquement sur la note, les étoiles, le graphe, les boutons primaires — rare = signifiant.
- ZIP parsé côté client ; aucune requête réseau après le chargement initial de la page.
- Modèle de donnée : `{ rating: number, date: string (ISO) }` — ne rien ajouter sans nécessité explicite.
- Phases 1→2→3 : rendu mocké (P1), données réelles (P2), gestion d'erreurs (P3) — ne pas mélanger.
## Jargon métier
- **Google Takeout** — export ZIP Google contenant les données du profil Google Business.
- **Avis / note** — évaluation étoilée (1–5) laissée sur Google Business.
- **Boulanger indépendant** — utilisateur cible : non-technicien, mobile-first, zéro tolérance pour la complexité.
#
Conventions 2 

- Pour toute API ou librairie externe, consulte Context7 avant d'écrire. Pas d'invention de signature de mémoire.
- Tout écran nouveau ou modifié doit être validé par un test Playwright avant que tu déclares "terminé".
- Toute modification de données en base passe par le CLI Supabase, jamais de SQL direct. Toujours une lecture de vérification avant tout ajout ou changement.












^G Get Help        ^O WriteOut        ^R Read File       ^Y Prev Pg         ^K Cut Text        ^C Cur Pos         
^X Exit            ^J Justify         ^W Where is        ^V Next Pg         ^U UnCut Text      ^T To Spell   
