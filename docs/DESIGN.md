# Design System — Analyseur d'avis Google

## Product Context
- **Quoi** : Outil monopage qui charge un export ZIP Google Takeout et affiche la note moyenne et l'évolution mensuelle des avis Google Business.
- **Pour qui** : Boulanger propriétaire d'une boutique indépendante, peu à l'aise avec les outils numériques, consulte depuis son téléphone en fin de journée.
- **Espace** : Petits commerçants / self-service analytics — distinct des outils agence (Podium, BrightLocal) qui ciblent des marketers multi-établissements.
- **Type** : Web app ultra-simple, zéro installation, mobile-first, fichier statique.
- **Memorable thing** : « un visuel chaud rassurant »

## Aesthetic Direction
- **Direction** : Organic-Minimal — austérité structurelle, chaleur venant exclusivement de la palette et de la typographie.
- **Décoration** : minimal — zéro ornement, Fraunces porte l'émotion sur le chiffre central.
- **Mood** : Chaleur artisanale sans pittoresque. Le fond parchemin et l'accent ambré évoquent le métier sans le caricaturer. La mise en page colonne unique dit : ce n'est pas un dashboard, c'est une réponse.

## Typography
- **Display/Hero** : Fraunces (variable, opsz 9–144, weight 600) — serif à chasse optique, caractère artisanal sans être rustique. Utilisé exclusivement sur le chiffre de note central pour transformer une métrique en verdict.
- **Body** : Instrument Sans 400/500 — humaniste, lisible à 16px sur mobile, ni froid ni corporate.
- **Data/Tables** : DM Sans (tabular-nums) — pour les labels d'axe, compteurs et tableaux.
- **Code** : N/A — pas de contexte code dans cet outil.
- **Loading** : `https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,300;9..144,400;9..144,600;9..144,700&family=Instrument+Sans:wght@400;500;600&family=DM+Sans:opsz,wght@9..40,400;9..40,500;9..40,600&display=swap`
- **Scale** : 10 / 11 / 12 / 13 / 14 / 16 / 20 / 28 / 68 px

## Color
- **Approche** : restrained — 1 seul accent ambré, la couleur apparaît sur la note et les étoiles uniquement. Rare = signifiante.
- **Primary** : `#D4762A` — accent ambré (croûte), utilisé sur le chiffre de note, les étoiles, le graphe, les boutons primaires.
- **Accent soft** : `#FFF0E2` — fond de la carte note et zones de dépôt de fichier.
- **Neutrals** :
  - `#FEFAF4` — fond page (parchemin)
  - `#FFFDF9` — surface carte
  - `#EBD5C2` — bordures et séparateurs
  - `#B89080` — texte tertiaire / labels
  - `#7A5C4E` — texte secondaire
  - `#2C1810` — texte primaire (brun profond, pas noir)
- **Semantic** : success `#3E6E4E`, warning `#9A6200`, error `#B83A1A`, info `#2C5F8A`
- **Semantic backgrounds** : success `#EDF6F0`, warning `#FFF8E6`, error `#FDF0EC`, info `#EDF4FB`
- **Dark mode** : non prévu dans cette version.

## Spacing
- **Base** : 8px
- **Densité** : confortable — l'outil ne doit pas écraser un boulanger qui consulte rapidement.
- **Scale** : 2xs(2) xs(4) sm(8) md(16) lg(24) xl(32) 2xl(48) 3xl(64)

## Layout
- **Approche** : grid-disciplined — colonne unique mobile-first, aucune sidebar, aucune navigation.
- **Grid** : 1 colonne sur tous les breakpoints.
- **Max content width** : 480px (centré).
- **Border radius** : sm:4px, md:10px, lg:16px, full:9999px

## Motion
- **Approche** : minimal-fonctionnel — uniquement les transitions qui aident la compréhension.
- **Easing** : enter(ease-out) exit(ease-in) move(ease-in-out)
- **Duration** : micro(50–100ms) court(150–250ms) moyen(250–400ms) long(400–700ms)
- **Usage** : fade-in des données au chargement du ZIP, dessin progressif du graphe (stroke-dashoffset). Rien d'autre.

## Decisions Log
| Date | Décision | Rationale |
|------|----------|-----------|
| 2026-06-25 | Création initiale | Fraunces serif sur le chiffre de note pour transformer une métrique en verdict artisanal. Fond parchemin #FEFAF4 — seul outil du marché à oser la chaleur vs blanc ou dark-mode. Colonne unique max 480px — réponse directe, pas dashboard. |
