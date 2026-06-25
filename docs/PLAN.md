# Plan : Analyseur d'avis Google pour boulanger indépendant

> PRD source : `docs/PRD.md`

## Décisions architecturales

Décisions durables qui s'appliquent à toutes les phases :

- **Runtime** : pur client-side — un seul fichier `index.html` + JS, sans serveur ni installation
- **Bundling** : aucun outil de build requis ; bibliothèques chargées depuis CDN
- **ZIP parsing** : JSZip
- **Graphe** : Chart.js, granularité mensuelle, axe temporel complet
- **Format Google Takeout** : fichier JSON des avis à l'intérieur du ZIP (chemin dépendant de la locale) ; chaque avis expose au minimum une note entière (1–5) et une date ISO
- **Modèle de donnée** : `{ rating: number, date: string (ISO) }` par avis
- **Déploiement** : fichier statique ouvrable directement dans le navigateur, aucun hébergement requis

---

## Phase 1 : Squelette visuel avec données mockées ✅

**User stories** : US-2, US-3, US-4

### Ce qu'on livre

Une page HTML responsive, ouvrable directement dans le navigateur sur mobile et desktop, qui affiche une note moyenne fictive (ex : 4,2 ★) et un graphe mensuel fictif couvrant plusieurs mois. Aucun fichier à charger — les données sont codées en dur. Cette phase valide le rendu complet de bout en bout : mise en page, composant de note, graphe d'évolution, responsive.

### Critères d'acceptation

- [x] La page s'ouvre sans serveur (protocole `file://` ou serveur local)
- [x] Une note moyenne est visible avec indication visuelle claire (étoiles ou chiffre)
- [x] Un graphe mensuel affiche au moins 6 points de données fictifs
- [x] La mise en page est lisible sur un écran mobile (≥ 375 px) sans défilement horizontal
- [x] La mise en page est lisible sur desktop

## Complétée le

2026-06-25

---

## Phase 2 : Chargement ZIP et données réelles

**User stories** : US-1, US-2, US-3

### Ce qu'on livre

Un bouton (ou zone de dépôt) permet de sélectionner le fichier ZIP exporté depuis Google Takeout. Après sélection, le ZIP est extrait côté client, le fichier JSON des avis est localisé et parsé, la note moyenne réelle est calculée et le graphe mensuel se construit sur l'intégralité de l'historique contenu dans le fichier. L'affichage mocké de Phase 1 est remplacé par les données vivantes. Le résultat s'affiche en moins de 5 secondes.

### Critères d'acceptation

- [ ] Un élément d'interface permet de sélectionner ou déposer un fichier ZIP
- [ ] Après chargement d'un ZIP Google Takeout valide, la note moyenne affichée correspond aux données réelles
- [ ] Le graphe mensuel couvre l'intégralité de l'historique présent dans le fichier (aucun filtre de date)
- [ ] L'affichage complet (note + graphe) apparaît en moins de 5 secondes après sélection du fichier
- [ ] L'outil fonctionne sans serveur, sans connexion réseau après chargement de la page

## Bloquée par

- Phase 1 (le rendu doit exister avant d'y brancher les données réelles)

---

## Phase 3 : Gestion d'erreurs

**User stories** : US-5

### Ce qu'on livre

L'outil détecte les cas où le fichier fourni ne peut pas être analysé — fichier non reconnu comme ZIP, ZIP valide mais sans données d'avis exploitables, ou fichier vide — et affiche à la place des indicateurs un message d'erreur explicite qui explique ce qui s'est passé et suggère quoi faire.

### Critères d'acceptation

- [ ] Charger un fichier qui n'est pas un ZIP affiche un message d'erreur explicite (pas de plantage silencieux ni d'écran blanc)
- [ ] Charger un ZIP valide ne contenant pas de données d'avis reconnaissables affiche un message d'erreur distinctif
- [ ] Charger un fichier vide affiche un message d'erreur
- [ ] Le message d'erreur indique la cause probable et une action corrective (ex : "Ce fichier ne contient pas d'avis Google reconnus. Vérifiez que vous avez exporté votre profil Google Business via Google Takeout.")
- [ ] Après une erreur, l'utilisateur peut relancer une sélection de fichier sans recharger la page

## Bloquée par

- Phase 2 (le parsing doit exister pour pouvoir intercepter ses cas d'échec)
