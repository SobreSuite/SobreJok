# SobreJoK

Des jeux old school pour les pauses café.

SobreJoK est le quatrième logiciel de la gamme Sobre (logiciels libres et légers), après SobreTeX, SobrePiX et SobrePdF. Il réunit quatre petits jeux de réflexion et de patience, qui se jouent en quelques minutes : **BiN** (ronds et lunes), **DeM** (le démineur), **ReX** (une couronne par zone) et **SoL** (le solitaire). L'interface reprend le style Mac 1-bit des années 1990 commun à toute la gamme.

## Pourquoi

Les jeux de pause sont partout, mais rarement tranquilles : applications chargées de publicités, jeux en ligne qui réclament un compte, sites qui enregistrent chaque partie. Pour cinq minutes entre deux réunions, c'est beaucoup.

SobreJoK choisit une autre voie :

- **tout reste sur l'ordinateur** : pas de compte, publicité et des scores qui ne quittent pas le navigateur ;
- **peu de jeux, bien faits** : quatre classiques, chacun avec son style et des indices qui expliquent leur raisonnement ;
- **un rendez-vous commun** : une grille/donne du jour mais aussi des possibilités de rejouer sans fin.

## Démarrer

SobreJoK tient dans un seul fichier HTML, sans installation, sans serveur et sans connexion.

1. Ouvrez `index.html` d'un double-clic dans Firefox ou Chrome.
2. La page d'accueil s'efface après 5 secondes, ou tout de suite au clic ou sur une touche.
3. Dans la fenêtre **Jeux**, cliquez sur un jeu. Ses règles s'affichent à la première partie, puis restent dans le menu **Aide**.
4. La case en haut à gauche de la fenêtre d'un jeu ramène aux Jeux. La partie en cours est gardée.

Le fichier fonctionne aussi depuis une clé USB ou une fois hébergé sur GitHub Pages. Tout est embarqué, police comprise : aucune ressource n'est chargée depuis Internet.

## L'interface

```
┌─ Barre de menus ── ▣ · Fichier · Édition · Affichage · Fenêtre · Aide ───────── 10:31 ─┐
│                                                                                        │
│  ┌─ Jeux ────────────────────────┐        ┌─ BiN · Grille du jour ──────────────────┐  │
│  │ ┌─────────────┐┌─────────────┐│        │ Du jour │ Moyen ▾ │ Nouvelle │ ↶ ↷ │ ?  │  │
│  │ │ BiN         ││ DeM         ││        ├─────────────────────────────────────────┤  │
│  │ │ du jour : ✓ ││ records     ││  ───▶  │                                         │  │
│  │ └─────────────┘└─────────────┘│        │            plateau de jeu               │  │
│  │ ┌─────────────┐┌─────────────┐│        │                                         │  │
│  │ │ ReX         ││ SoL         ││        │       post-it d'aide ou d'indice        │  │
│  │ │ en cours    ││ à faire     ││  ◀───  ├─────────────────────────────────────────┤  │
│  │ └─────────────┘└─────────────┘│        │ Temps · message · compteur              │  │
│  └─ 4 jeux ──────────────────────┘        └─────────────────────────────────────────┘  │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

- La fenêtre **Jeux** présente les quatre jeux, chacun avec son état : grille ou donne du jour à faire ou réussie, partie en cours, records par niveau.
- Chaque jeu a sa fenêtre : une barre d'outils (grille du jour, niveau, nouvelle partie, annuler, indice…), le plateau, puis une barre d'état avec le temps, un message et un compteur.
- Les menus : **Fichier** lance une nouvelle partie de n'importe quel jeu ; **Édition** (Annuler, Rétablir, Indice, Effacer…) agit sur le jeu affiché ; **Affichage** règle les erreurs signalées, le chrono et les options propres aux jeux ; **Fenêtre** passe d'un jeu à l'autre ; **Aide** donne les règles de chaque jeu.
- Les messages s'affichent dans la barre d'état, les indices dans un post-it jaune sous le plateau.
- Le chrono s'arrête quand l'onglet est caché, qu'un dialogue est ouvert ou qu'on revient aux Jeux. Il se masque dans **Affichage**.
- **Fichier › Quitter** ferme l'onglet quand le navigateur l'autorise, et affiche sinon un écran de fermeture.

## Les quatre jeux

| Jeu | Inspiré de | Le principe | Niveaux | Du jour |
|---|---|---|---|---|
| **BiN** | Takuzu, Tango de LinkedIn | Remplir une grille 6 × 6 de ronds rouges et de lunes bleues | Facile, Moyen, Difficile | Oui, niveau Moyen |
| **DeM** | Démineur | Ouvrir toutes les cases sans mine | Débutant, Intermédiaire, Expert | Non |
| **ReX** | Queens de LinkedIn | Placer une couronne par ligne, par colonne et par zone de couleur | Facile 6 × 6, Moyen 7 × 7, Difficile 8 × 8 | Oui, 7 × 7 |
| **SoL** | Solitaire Klondike | Ranger les 52 cartes de l'As au Roi | Pioche par 1 ou par 3 | Oui, pioche par 1, toujours gagnable |

### BiN : ronds et lunes

- **Règles** : chaque ligne et chaque colonne compte 3 ronds et 3 lunes ; jamais plus de deux symboles identiques côte à côte ; deux cases reliées par **=** portent le même symbole, par **×** des symboles opposés. Chaque grille a une seule solution, qu'on trouve en raisonnant, sans deviner.
- **Jouer** : clic = rond, puis lune, puis case vide ; clic droit dans l'autre sens. Les cases données au départ, sur fond tramé, ne changent pas.
- **Erreurs** : les cases fautives passent en jaune et la barre d'état dit quelle règle est enfreinte (désactivable dans **Affichage › Signaler les erreurs**).
- **Indice** : signale d'abord une erreur ou une case mal partie, sinon montre la déduction suivante et l'explique (« Deux ronds côte à côte : pas de troisième à la suite »).
- **Niveaux** : Facile se résout avec les règles directes ; Moyen demande de comparer les combinaisons possibles d'une ligne ; Difficile, de tester une hypothèse jusqu'à l'impasse.

### DeM : le démineur

- **Règles** : un chiffre indique combien de mines touchent la case, diagonales comprises. On gagne en ouvrant toutes les cases sans mine.
- **Niveaux classiques** : Débutant 9 × 9 et 10 mines, Intermédiaire 16 × 16 et 40 mines, Expert 30 × 16 et 99 mines. Sur petit écran, le champ Expert défile dans la fenêtre.
- **Premier clic sans danger** : les mines sont posées après lui, jamais sur la case cliquée ni autour. On démarre toujours sur une ouverture.
- **Jouer** : clic = ouvrir ; clic droit ou appui long au doigt = drapeau ; clic sur un chiffre qui a tous ses drapeaux = ouvrir ses voisines. Le bouton **Drapeau** fait poser un drapeau à chaque clic, pratique sur téléphone.
- **Chiffres** aux couleurs de la gamme : 1 bleu, 2 rouge, 3 jaune (sur carré noir, pour rester lisible), 4 vert, 5 orange, 6 violet, 7 noir, 8 gris.
- **Le visage** au centre sourit, fait « oh » pendant l'appui, met ses lunettes de soleil à la victoire et ferme les yeux en croix à la défaite. Un clic dessus relance une partie.

### ReX : une couronne par zone

- **Règles** : une couronne par ligne, par colonne et par zone de couleur ; deux couronnes ne se touchent jamais, pas même en diagonale. Une seule solution, trouvable sans deviner.
- **Couleurs** : les zones prennent les six couleurs de la gamme (rouge, bleu, vert, orange, violet, gris), plus une zone blanche en 7 × 7 et une zone tramée en 8 × 8. Le jaune est réservé à la couronne. Des filets noirs épais séparent les zones, qui restent lisibles sans les couleurs.
- **Jouer** : clic = croix, puis couronne, puis case vide ; glisser = poser ou retirer des croix sur plusieurs cases d'un coup ; clic droit = couronne directe.
- **Erreurs** : la ligne, la colonne ou la zone fautive se couvre de hachures, et la barre d'état dit pourquoi.
- **Croix automatiques** (dans **Affichage**, désactivées au départ) : les cases interdites par les couronnes posées se marquent d'une croix pâle.
- **Indice** : comme dans BiN, la déduction suivante avec son explication (« La zone verte tient entièrement dans la colonne 3 : les autres cases de la colonne 3 sont exclues »).

### SoL : le solitaire

- **Règles** du Klondike : dans les sept colonnes, on empile en descendant et en alternant rouge et noir ; seul un Roi, ou une suite qui commence par un Roi, va sur une colonne vide ; les quatre fondations se montent de l'As au Roi, une par enseigne. Tours de pioche illimités.
- **Pioche par 1 ou par 3**, au choix dans la barre d'outils. En pioche par 3, les cartes retournées s'affichent en éventail.
- **Jouer** : glisser une carte ou une suite, à la souris ou au doigt ; un clic sur une carte l'envoie à la meilleure place, la fondation d'abord (un double-clic par habitude ne joue qu'un coup) ; un clic sur la pioche retourne des cartes ; le bouton **Fondations** range tout ce qui peut l'être.
- **Fin automatique** : quand toutes les cartes sont visibles et la pioche vide, SoL range le reste tout seul.
- **Victoire** : les cartes partent en cascade et rebondissent, comme dans le solitaire de Windows. Un clic arrête la cascade et ouvre le bilan.
- **Cartes** : enseignes en pixel art ; figures marquées d'une lettre (R, D, V) et d'un emblème : la couronne de ReX pour le Roi, un diadème pour la Dame, une plume pour le Valet. Dos à la trame du bureau. **Affichage › Jeu quatre couleurs** passe le carreau en bleu et le trèfle en vert (pour l'alternance, le carreau compte toujours comme rouge et le trèfle comme noir).

## Grilles du jour et records

| Mécanisme | Rôle |
|---|---|
| Grille ou donne du jour | Tirée de la date : la même pour tout le monde ce jour-là, à version égale du fichier. Une fois réussie, elle s'affiche résolue avec son temps jusqu'au lendemain. |
| Records | Meilleur temps par niveau. Pour BiN et ReX, seulement les grilles résolues sans indice. Pour SoL, un record en pioche par 1 et un en pioche par 3. |
| Partie en cours | Chaque jeu reprend sa partie au lancement suivant, là où on l'avait laissée. |
| Annuler / Rétablir | Sans limite pendant la partie dans BiN, ReX et SoL. Le démineur n'a pas d'annulation, comme l'original. |
| Où tout cela est gardé | Dans le stockage local du navigateur (`localStorage`, clé `sobre-jok:v1`), sur cet ordinateur seulement. Un autre navigateur ou une navigation privée repartent de zéro, et effacer les données de navigation efface les records. |

## Raccourcis clavier

SobreJoK affiche ⌘ sur Mac et Ctrl sur Linux et Windows. Les touches d'un jeu agissent quand son plateau est sélectionné : un clic dessus suffit.

| Action | Mac | Linux / Windows |
|---|---|---|
| Annuler / Rétablir (BiN, ReX, SoL) | ⌘Z / ⇧⌘Z | Ctrl+Z / Ctrl+Y |
| Indice (BiN, ReX) | H | H |
| Se déplacer dans la grille (BiN, DeM, ReX) | Flèches | Flèches |
| BiN : poser un rond / une lune | R ou 1 / L ou 2 | R ou 1 / L ou 2 |
| BiN, ReX : changer le contenu de la case (Maj : dans l'autre sens) | Espace | Espace |
| BiN, ReX : vider la case | Retour arrière ou Suppr | Retour arrière ou Suppr |
| ReX : croix / couronne | X / C | X / C |
| DeM : ouvrir / drapeau | Espace / F | Espace / F |
| SoL : piocher | Espace | Espace |
| SoL : tout envoyer aux fondations | F | F |
| Fermer un menu ou un dialogue | Échap | Échap |
| Valider le bouton par défaut d'un dialogue | Entrée | Entrée |

Fermer et Quitter n'ont pas de raccourci : ⌘W, ⌘Q, Ctrl+W et Alt+F4 appartiennent au navigateur ou au système, et aucune page web ne peut les intercepter.

## Choix techniques

- **Un seul fichier HTML autonome** (environ 197 Ko), écrit à la main en HTML, CSS et JavaScript, sans bibliothèque ni étape de compilation.
- **Graphismes** : tout le pixel art (ronds, lunes, mines, drapeaux, visage, couronne, enseignes, figures) est dessiné en SVG par le code, à partir de petites grilles de pixels. La seule image est le logo de l'accueil (PNG de 10 Ko). La cascade de cartes de SoL est dessinée dans un canvas.
- **Hasard reproductible** : la grille du jour naît d'un générateur pseudo-aléatoire initialisé par la date (hachage FNV-1a, générateur mulberry32). Même date et même version du fichier donnent la même grille sur tous les postes.
- **BiN** : une rangée valide n'a que 14 formes possibles. Le générateur tire une solution, puis retire symboles et signes tant que la grille reste résoluble par un solveur logique limité au niveau demandé. Les indices reprennent ce solveur, d'où leurs explications.
- **ReX** : couronnes placées au hasard, zones qui poussent autour de chacune, puis recherche exhaustive des solutions et retouche des zones jusqu'à ce qu'il n'en reste qu'une. Le même type de solveur logique, à trois niveaux, règle la difficulté et produit les indices.
- **SoL** : la donne du jour passe par un solveur. En pioche par 1 avec des tours illimités, chaque carte de la pioche finit par être accessible, et une partie dont toutes les cartes sont retournées est forcément gagnée : le solveur cherche donc un chemin jusqu'à ce point. Il est prudent : quand il répond « gagnable », c'est sûr. Ses solutions ont été rejouées avec les vraies règles : 45 donnes, 45 victoires.
- **Chrono** : temps cumulé par partie, mis en pause selon la visibilité de l'onglet et les dialogues.
- **Stockage** : `localStorage` pour les préférences, les records, les grilles et donnes du jour réussies (60 derniers jours) et les parties en cours (pour SoL, la donne de départ et les 40 derniers coups).
- **Accessibilité** : dans BiN, DeM et ReX, chaque case est un bouton décrit pour les lecteurs d'écran (ligne, colonne, contenu). Les animations sont coupées quand le système demande moins de mouvement.
- **Police de l'interface** : Pixelify Sans (SIL Open Font License 1.1), embarquée et corrigée : Z redessiné, 5 redessiné (il ressemblait à un S), © à pleine taille, ligatures retirées.

## Limites connues (V0.1)

- La grille du jour n'est identique entre collègues qu'avec la même version du fichier : une évolution du générateur change les grilles.
- Les scores restent dans chaque navigateur : pas de classement partagé.
- Aucun moyen d'effacer les records. Les parties jouées avant la correction du chrono (17 octobre 2026) ont pu enregistrer des temps faux.
- ReX : le niveau Difficile se distingue surtout par sa taille ; environ une grille 8 × 8 sur deux demande vraiment une hypothèse, les autres se résolvent par déduction directe.
- DeM : pas de point d'interrogation sur les cases douteuses, pas de grille du jour.
- SoL : se joue à la souris ou au doigt, pas carte par carte au clavier ; pas de score en points ; pas d'alerte quand plus aucun coup n'est possible ; seule la donne du jour est garantie gagnable.
- Navigateurs : testé dans Chromium, sur grand écran et sur téléphone. Le comportement dans Firefox reste à vérifier, en particulier le stockage local d'un fichier ouvert depuis le disque.

## Feuille de route

- Tester et corriger dans Firefox (Linux et Windows).
- Effacer les records, par jeu ou en bloc.
- Partager son résultat du jour en une ligne à copier (« BiN du 17 octobre : 2 min 41 s, sans indice »).
- Statistiques par jeu : parties jouées et gagnées, séries de jours.
- SoL : jeu au clavier, alerte quand la partie est bloquée.
- DeM : point d'interrogation sur les cases douteuses.
- Reporter la correction du 5 de Pixelify Sans dans SobreTeX, SobrePiX et SobrePdF.
- Version installable (PWA) : icône, fenêtre dédiée, hors ligne.
- Choisir et publier une licence libre (l'EUPL est envisagée).

## Licence

Licence libre EUPL envisagée. © 2026 Auraponymous.

Composant tiers embarqué dans `SobreJoK.html`, sous sa propre licence :

| Composant | Auteur | Licence |
|---|---|---|
| Pixelify Sans | The Pixelify Sans Project Authors | SIL Open Font License 1.1 |
