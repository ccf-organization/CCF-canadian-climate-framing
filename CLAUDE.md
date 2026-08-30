<!-- COPIE GÉNÉRÉE — NE PAS ÉDITER ICI.
     Source unique : CCF-website (dépôt privé ccf-web), fichier CLAUDE.md à la racine.
     Toute modification se fait là-bas puis se recopie ici à l'identique.
     Ce dépôt-ci est le dépôt scientifique (papier Scientific Data + données publiées) :
     le canon s'y applique à toute prose, figure ou page produite pour le papier. -->

# CANON CCF — règles de maison, identité et charte

> **Ce fichier est la source d'autorité du projet CCF.** Il est chargé automatiquement dans
> chaque session. Lis-le en entier avant d'écrire une ligne de code, de prose ou de CSS.
> Il vaut pour le site, l'observatoire, les notes d'analyse, l'infolettre, les courriels, les
> cartes sociales, les publications Bluesky et le papier scientifique.
>
> **Version du canon : 1.0 — 2026-08-30.** Établi par audit du code réel (8 agents, 757 faits
> vérifiés). Chaque valeur porte son adresse : si le code a changé, **le code gagne** — corrige
> alors ce fichier dans la foulée.

## 0. Comment ce fichier s'utilise

**Ordre d'autorité, sans exception : le code > ce canon > les skills > la mémoire.**
Une règle vue ici mais contredite par le code en production : le code fait foi, et tu signales
l'écart. Une règle absente d'ici mais présente dans un skill : elle s'applique quand même — les
skills `esthetique-ccf` et `redaction-ccf` (dans `.claude/skills/`) portent le détail opératoire
que ce canon résume. Une règle qui n'existe que dans une note de mémoire : traite-la comme une
observation datée, pas comme une loi.

**Les deux skills se chargent avant tout travail visuel ou rédactionnel** — ce n'est pas
facultatif : `esthetique-ccf` avant de toucher au CSS, aux gabarits ou à toute page ;
`redaction-ccf` avant d'écrire de la prose destinée à être publiée (note, infolettre, encart,
courriel, message social), y compris un court paragraphe.

**Périmètre des dépôts.** Le serveur et l'observatoire vivent dans `/Users/antoine/Servers/ccf-web`
(dépôt privé) ; `~/Documents/Github/ccf-web` est un **lien symbolique** vers lui — travaille
toujours depuis `Servers/` (le chemin par le lien ouvre une mémoire de projet différente et vide).
Le papier et les données vivent dans `~/Documents/Github/CCF-canadian-climate-framing` (dépôt
public), qui reçoit une copie de ce canon.

---

## 1. Identité

**Ce qu'est CCF.** L'observatoire du cadrage médiatique climatique canadien : une base annotée
(283 964 articles, 22 médias, 1978-2026, 9,9 M d'unités de deux phrases annotées par 128
classifieurs), un site public (ccf-project.ca), un pipeline continu qui l'alimente, et un papier
de méthode (Scientific Data). Le produit est **scientifique**, pas militant.

**Pour qui on écrit.** Un partenaire exigeant : chercheur, ministère, ONG, journaliste. Il lit
vite, connaît le sujet, et détecte immédiatement deux choses — l'imprécision et la prose générée.

**La voix.** Sobre, factuelle, humaine. Institutionnelle sans être raide. On montre les chiffres
et on assume les limites ; on ne vend rien.

**Vocabulaire imposé** (contraventions fréquentes) :

| On dit | Jamais |
|---|---|
| acteurs climatiques | partenaires |
| L'état du débat / The state of the debate | signal (le mot est banni de toutes les surfaces) |
| Le résumé CCF | digest |
| des phrases où la science est en cause | des articles qui questionnent la science |
| Français et anglais / English and French | FR/EN dans l'interface publiée |
| articles annotés, phrases en cause, arguments | formules vagues sans unité de compte |

On compte les **arguments** (avec leur fenêtre) et les **phrases** en cause — jamais les articles,
qui ne font que les rapporter.

---

## 2. Les interdits absolus

Ces règles ont été posées par Antoine, souvent après avoir été enfreintes. Aucune n'est
négociable, et aucune ne se contourne « juste cette fois ».

1. **Aucun liseré ni barre d'accent colorée** comme différenciateur : pas de `border-top`
   ni `border-left` teinté de 2-3 px, pas de tick vertical, pas de bande latérale. Motif : « ce
   n'est pas dans le langage visuel du site », et ça fait immédiatement « généré ». On différencie
   par **l'icône d'onglet et la couleur de catégorie**. Seule exception tolérée : un liseré **bas**
   de 2 px en `inset box-shadow` (`--ccf-action-signature`, atlas-shell.css). Un `border-left:1px`
   de séparateur de tableau n'est pas un liseré d'accent (seuil d'audit : ≥ 2 px).
2. **Aucun emoji dans l'interface, les courriels, les PDF ou la prose scientifique.** Le registre
   graphique autorisé est typographique : ✦ (U+2726, la signature de clic), ✕ ✓ ✎ ❖ ☰ et les
   figures géométriques des vues (◧ ◈ ◎ ⇲ ▤ ▦ ▥ ◐ ▧ 〜). Bluesky est la seule surface où un
   registre fermé d'emojis sert de signalétique (🌍 journal, 📊 pouls, 🏅 figures, 🎙 voix, ⚡ éclair).
3. **Aucune flèche → dans la prose.** On écrit « de 3,6 à 15,0 % » / « from 3.6 to 15.0% ». La
   flèche appartient aux **figures** : étiquettes de valeurs, infobulles, légendes « pré → post ».
4. **Jamais retarder l'en-tête d'une page.** Le titre du héros s'anime mot à mot immédiatement
   (spans `.w`, 0,03 s × i, terminé sous 0,8 s) ; question à 0,28 s, méta et boutons à 0,42 s.
   Aucune opacité différée sur le h1, le kicker ou la description.
5. **Toute animation a une issue `prefers-reduced-motion`.** Sans exception.
6. **Aucun défilement horizontal du corps de page** : `html,body { max-width:100vw;
   overflow-x:hidden; overflow-x:clip }`. Le `clip` est délibéré — il évite de créer un conteneur
   de défilement, ce qui casserait le `position:sticky` du rail de l'observatoire. Toute table
   large vit dans un `.tblwrap` en `overflow-x:auto`.
7. **Aucun blanc en bas ni à droite d'un encart de PDF** (« règle d'or ») : les deux colonnes
   ferment ensemble, par égaliseur automatique.
8. **Les encarts font la largeur du texte**, jamais plus large.
9. **Langues écrites en toutes lettres** partout dans l'interface publiée.
10. **Ne jamais réintroduire** les positions par rôle et les sous-parties « Ce qu'ils contestent /
    défendent / Ce qu'on leur reproche » : supprimées du produit science sur demande explicite.

---

## 3. La marque

### 3.1 Le symbole

Le symbole CCF est un **phare dans un médaillon circulaire** (cercle `r=245`, contour `#0E2A47`,
décor mis à l'échelle 1.2 depuis le centre). Il remplace un logo hérité en feuille d'érable qui
**ne doit plus jamais être utilisé** (voir 3.4).

Dossier canonique : `static/assets/logos/` (24 fichiers).

| Fichier | Format | Usage |
|---|---|---|
| `ccf_icone.svg` / `.png` (1024²) | icône couleur | chips des PDF et encarts web, cartes OG, courriels de compte |
| `ccf_icone_mono.svg` | icône monochrome `#0E2A47` | usages une couleur (le `.png` est orphelin) |
| `ccf_paysage_{en,fr}.svg` / `.png` (1920×600) | lock-up paysage 3,2:1 | masthead des PDF de note ; le PNG ne sert que de repli d'erreur des cartes OG |
| `ccf_vertical_{en,fr}.svg` / `.png` | lock-up vertical | **orphelins** — disponibles, jamais employés |
| `ccf_banniere_{en,fr}.svg` / `.png` (1500×500) | bannière fond sombre | **orphelins** — le fond `#0E2A47` est cuit dans le fichier |
| `ccf_favicon_{32,64,180,512}.png` | favicons | `<head>` (32/64/512 + apple-touch 180) ; le 512 sert aussi de médaillon d'infolettre et de signature des cartes Bluesky |

**Typographie du mot-symbole** (dans les SVG de lock-up) : Avenir Next / Futura / Century Gothic,
poids 600 ; « CANADIAN CLIMATE FRAMING » à 33 px, interlettrage 1,2 ; filet d'accent `#E8A33D`,
épaisseur 3,5, extrémités rondes. Baseline « MEDIA OBSERVATORY » / « OBSERVATOIRE MÉDIATIQUE ».

**Palette de la marque** (valeurs des SVG, distinctes de la palette du site) : bleu nuit
`#0E2A47` · or des faisceaux `#F7C860` · blanc cassé `#F5F7F8` · ambre du filet `#E8A33D` ·
dégradé de ciel `#6E9FBB → #B9D2DD → #F0EBDD → #E9B87E → #C4602F`.

### 3.2 Le logo vivant

Le logo affiché en en-tête, en pied et en filigrane de héros n'est **aucun fichier statique** :
c'est un SVG inline animé, `templates/includes/logo_live.html`, inclus par Jinja. Cycle de 24 s en
scènes (blizzard, pluie battante, canicule aux faisceaux blancs, montée des eaux, incendie) ;
keyframes `.ccflogo__*` dans `main.css`, coupées sous `prefers-reduced-motion`.

**Piège :** le paramètre `lid` doit être **unique par instance** (il suffixe tous les identifiants
SVG) — instances existantes : `nav`, `bcn`, `ft`, `wm`. Deux instances au même `lid` collisionnent.

**Dette connue :** le tracé du logo vivant existe en quatre copies indépendantes (gabarit Jinja,
template inline de l'explorateur, `data-server/explorer/assets/ccflogo.svg.html` orphelin, et les
SVG statiques). Une retouche du dessin demande quatre modifications.

### 3.3 Le phare de kicker (à ne pas confondre)

`.ccf-lh` est un **glyphe distinct** du logo : viewBox 24×24, rempli en `currentColor`, centralisé
dans `templates/includes/kicker_lh.html`. Ce n'est pas le médaillon (`.hero__logo-medal`, le logo
vivant animé de 84-122 px qui ouvre les héros). Voir 5.1.

### 3.4 Marque héritée — bannie

`static/assets/images/CCF_icone.png` (feuille d'érable, demi-globe, flocon) et sa variante
`CCF_icone_dark.png` sont l'**ancienne** marque. **Ne jamais les utiliser.** Piège de nommage :
`logos/ccf_icone.png` = phare (actuel) ; `images/CCF_icone.png` = feuille d'érable (hérité).

**Dette ouverte :** ce logo hérité est encore en production sur `data.ccf-project.ca` (favicon,
og:image, écran de connexion admin, TOTP, tableau de bord). Tant qu'il y est, deux marques
coexistent — à corriger dès qu'on touche à l'explorateur.

### 3.5 Ce qui manque à la charte

À produire un jour, en connaissance de cause : version blanche (knockout) de l'icône ; mot-symbole
vectoriel sur fond sombre réutilisable ; `favicon.ico` et manifeste web ; spécification de marque
(zone de protection, taille minimale, usages interdits, CMJN/Pantone) ; avatar et bannière aux
formats réseaux ; dérivés optimisés des portraits d'équipe (1,2 à 2,1 Mo pièce aujourd'hui).

---

## 4. Le système visuel

### 4.1 Où vit le CSS

Deux feuilles sur **toutes** les pages, dans cet ordre : `static/css/main.css` (3 435 lignes, la
source canonique) puis `atlas-shell.css` (la coquille du registre récent). Toute autre feuille est
ajoutée par sa page via `extra_css` : `home-concepts.css` (accueil publié, variante
`research-refined`), `about-atlas.css`, `team-atlas.css`, `contact-atlas.css`,
`database-atlas.css`, `services-newsletter.css`, `observatory-atlas.css`, `obs-rail.css`.

**Le rail de l'observatoire a une source unique déclarée** : `obs-rail.css`. Ne le restyle nulle
part ailleurs.

**Cache-busting obligatoire** : les CSS sont servis avec `max-age` 7 jours et un `?v=`. **Modifier
un CSS sans bumper le `?v=` livre du périmé au visiteur** — c'est la cause classique du « ce n'est
pas corrigé chez moi ». Bumper dans les deux langues.

### 4.2 Les trois registres chromatiques

Le site parle **trois palettes** selon la génération de page. Ne les mélange pas dans une même vue.

**Registre 1 — variables `:root` de `main.css` (l. 8-108), la fondation.**
Océan/neige : `--color-deep-ocean #0a1628` · `--color-ocean #0d2137` · `--color-arctic #e8f4f8`
(fond du corps) · `--color-snow #f5f9fa` · `--color-frost #ffffff`.
Forêt : `--color-forest-dark #1a3a2f` · `--color-forest #2d5a4a` · `--color-forest-light #3d7a64`
· `--color-moss #5c8a6e` · `--color-sage #7aa589`.
Aurore : `--color-aurora-green #00d4aa` · `--color-aurora-teal #00b4c5` ·
`--color-aurora-blue #0095c8` · `--color-aurora-purple #7b68ee` · `--color-aurora-pink #ff6b9d`.
Terre : `--color-earth-dark #2c2416` (l'encre du corps) · `--color-earth #4a3f35` ·
`--color-bark #6b5b4d` · `--color-sand #c4b49a` · `--color-wheat #e8dcc8`.
Données climat : `--color-warming #ff6b6b` · `--color-cooling #4ecdc4` · `--color-carbon #2c3e50`
· `--color-renewable #27ae60` · `--color-alert #f39c12`.

*Piège :* `--color-ocean-deep`, `--color-surface` et `--color-text-muted` sont **utilisées mais
jamais déclarées** — elles ne fonctionnent que par leur valeur de repli écrite à chaque appel.
N'en ajoute pas d'autres ; si tu en croises une sans repli, la déclaration est invalide.

**Registre 2 — les verts d'action (littéraux, hors variables).**
`#0c7460` : le vert du **kicker de section** en mode clair (170 occurrences).
`#0f8a76` : le vert d'**interaction** (survols, pastilles actives, bordures actives).
Dégradé d'action récurrent : `linear-gradient(135deg, #0f8a76, #12b48c)`.

**Registre 3 — « Atlas », les pages refaites** (accueil, à propos, équipe, contact, base et
méthode, observatoire, coquille) : plus sombre et mat. Forêt profonde `#12362d` · accent `#17604f`
· menthe `#a6dac9` · papier `#e8ede7`. Encre `#173a30`, texte secondaire `#66766f`, filets
`#b4c6bd` / `#d2ddd7`.

**Les pages d'analyses ont leur propre déclinaison, plus sombre :** kickers et boutons `#0a5c4a`,
encre de titre `#0e2a1f`, corps `#24382e`, secondaire `#3d5147`, méta `#5c7166`, filets `#7d938a`
/ `#9eb6ab`, et la **braise `#b0492f`** pour l'alerte, le recul et les mentions bêta.

### 4.3 Couleur sémantique — la règle transversale

**Le vert forêt dit le gain, la présence, la défense. La braise dit le recul, l'alerte, la
contestation.** Deux teintes suffisent à coder tout le sens des figures : c'est ce qui rend une
note lisible comme un système.

Les **couleurs par cadre** diffèrent selon le support (trois jeux distincts, assumés) :
*vive* pour les graphiques de l'observatoire (culture `#9b59b6`, économie `#3498db`,
environnement `#00d4aa`, santé `#27ae60`, justice `#f1c40f`, politique `#e74c3c`, science
`#1abc9c`, sécurité `#34495e`) ; *feutrée* pour le pouls médiatique — celle que voit le visiteur
(politique `#c0533f`, économie `#b9862e`, environnement `#0f8a76`, santé `#5f9a63`, justice
`#8a68a8`, science `#47809f`, sécurité `#64748b`, culture `#a86f8e`) ; *profonde et désaturée*
pour l'infolettre (motif écrit : « les vifs faisaient arc-en-ciel »).

### 4.4 Mode sombre

Attribut `data-theme="dark"` sur `<html>`, **jamais** de `@media (prefers-color-scheme)` — le
thème est posé avant peinture par un script inline lisant `localStorage['ccf-theme']`. Bascule :
`#themeToggle`, dont le libellé est un caractère (☀ / ☽).

Racine sombre : fond `#0a1628`, texte `#e0dcd6`. Titres `#e0dcd6`, paragraphes `#c4bfb8`, méta
`#9a8e82`. Le vert d'accent bascule : `#0c7460` → `#7fe9cf` pour les kickers, `#00d4aa` pour liens
et boutons. Cartes : `rgba(20,30,46,0.85)`, bord `rgba(0,212,170,0.12)`.

*Piège :* le filet de sécurité des cartes sombres utilise
`[class*="card"]:not([class*="card__"])` — le `:not()` exclut délibérément les sous-éléments BEM.
Sans lui, chaque titre et badge reçoit son propre rectangle sombre (« effet pavés »).

### 4.5 Typographie

Quatre familles, une seule requête Google Fonts, `display=swap` :

| Jeton | Famille | Rôle réel |
|---|---|---|
| `--font-display` | **Lora**, Georgia, serif | titres, gros chiffres en filigrane, sous-titres en italique |
| `--font-sans` / `--font-body` | **Archivo** | corps, kickers, boutons, méta, étiquettes |
| `--font-prose` | **Source Serif 4** | prose longue (lede d'accueil, encart récit, descriptions) |
| `--font-mono` | **Space Grotesk** | dates, compteurs, axes, codes, données tabulaires |

`--font-mono` **n'est pas** une chasse fixe (Space Grotesk est proportionnelle) : le nom du jeton
est trompeur. Règle écrite dans `atlas-shell` : les **étiquettes éditoriales** passent à la sans
humaniste ; la « mono » reste réservée aux dates, compteurs, axes, codes.

Corps : 1,0625 rem (17 px), interligne 1,75, encre `#2c2416` sur fond `#e8f4f8`. Racine 16 px,
`scroll-padding-top: 96px` (nav flottant), `-webkit-text-size-adjust:100%` (sans quoi iOS gonfle
les petits textes des chips).
Titres : h1 `clamp(2.5rem, 6vw, 4rem)` poids 700 ; h2 `clamp(1.875rem, 4vw, 2.75rem)` ; h3
`clamp(1.5rem, 3vw, 2rem)` ; communs : Lora, poids 600, interligne 1,2, `letter-spacing -0.02em`,
couleur `--color-ocean`.
`text-wrap: balance` sur les titres, `pretty` sur les paragraphes légaux.

### 4.6 Jetons

Espacement `--space-xs .25rem` → `--space-5xl 8rem`. Conteneurs 800 / 1200 / 1400 px (les pages
récentes préfèrent `min(1200px, calc(100% - 48px))`). Rayons 4 / 8 / 16 / 24 px, pilule 999 px,
plus `--ccf-action-radius 10px` pour le registre Atlas. Transitions nommées : `--transition-breeze
.3s`, `wave .5s`, `tide .8s`, `organic .6s` (rebond).

*Constat :* les composants récents n'utilisent pas ces jetons — ils écrivent 0,15-0,25 s pour les
survols et 0,45-0,95 s pour les entrées, et des ombres vertes très diffuses
(`0 18px 50px -22px rgba(8,40,32,.35)`) plutôt que les ombres bleu marine nommées. Aligne-toi sur
le voisinage de la page que tu touches, pas sur les jetons historiques.

---

## 5. Les composants signature

### 5.1 Le kicker au phare — le composant identitaire

**Grammaire canonique :** phare + libellé, **police du corps**, `.7rem`, poids 700,
`letter-spacing .12em`, majuscules, vert `#0c7460` (sombre `#7fe9cf`), phare 14 px, `gap 8px`.

Usage : `<span class="…__k">{% include 'includes/kicker_lh.html' %}Libellé</span>`.

Le SVG (`kicker_lh.html`) : `.ccf-lh` en 15×15, `fill: currentColor` sur toutes les formes — c'est
**le conteneur qui porte la teinte**. La variante de tête de kicker `.ccf-lh--k` vaut
`vertical-align:-.16em; margin-top:-1px` : le libellé étant en capitales, son centre optique siège
au-dessus du milieu de ligne, et un phare centré paraîtrait tomber.

Les faisceaux clignotent alternativement sur 2,6 s (invisibles au repos, `opacity .8` aux pics) ;
sous `prefers-reduced-motion`, animation coupée et opacité fixée à 0,45.

### 5.2 L'étoile polaire ✦ — la signature de clic

Texte pur (U+2726), jamais un SVG, jamais un emoji : fiable dans toutes les injections, y compris
les clients de messagerie. Elle **guide, comme le phare**. Emplois : flèche des rangées d'index,
suffixe des appels à l'action, marque du journal, puce des cartes de cascade. Sur les cartes de
notes, elle apparaît au survol (`content:'✦ Ouvrir la note'`, glissement de 6 px) ; sur les boutons
de héros, elle glisse en 0,25 s.

### 5.3 Le bouton de verre `.btn-lh` — le bouton unique

Une seule définition, dans `main.css` (« ne pas dupliquer ailleurs »), appliquée à sept familles de
sélecteurs (`.btn-lh, .btn, .db-btn, .abt-btn, .contact-btn, .svc-cta__btn, .holp__cta`).

Recette : rayon 999 px ; fond `linear-gradient(180deg, rgba(255,255,255,.22), transparent 48%)`
posé sur `color-mix(in srgb, var(--tnt,#fff) 9%, rgba(255,255,255,.55))` ; `backdrop-filter:
blur(22px) saturate(180%)` ; bord `color-mix(--tnt 20%, rgba(255,255,255,.65))` ; ombre interne
haute. Géométrie : `inline-flex`, `gap 8px`, `padding 14px 26px`, `600 13.5px/1.2` en police de
corps ; phare intégré 16×16.

**La teinte porte le sens**, via `--tnt` : `#0e9c86` = continuer/agir · `#2a7fb8` = naviguer ·
blanc = neutre/secondaire. Aucune couche héritée n'est tolérée (`::before/::after` forcés à
`content:none !important` — « plus de lumière voyageuse »).

Variante sur fond sombre `.btn-lh--ondark` (« nos boutons préférés ») : texte `#f2fbf7`, fond
`rgba(255,255,255,.10)`, bord `rgba(255,255,255,.36)`, **rayon 12 px** (pas la pilule),
`blur(20px)`, et au survol un `translateY(-2px)`.

Deux exceptions écrites : `.btn--primary` garde son dégradé vert signature (demande explicite,
c'est le CTA principal de l'observatoire) et `.holp__cta` épouse la carte de l'encart d'accueil.
Sur les pages base-et-méthode, la forme passe en rayon 12 px et 44 px de haut pour s'aligner sur le
registre Atlas.

### 5.4 L'encadré CCF

**Toujours : fond très pâle + filet fin + petit rayon.** Jamais un pavé pastel arrondi.
PDF `#eef3ee` / 1 px `#cfdccf` / rayon 4 px · page `#eef3ee` ou blanc / 1 px `#cfdccf` / rayon
6 px · infolettre `#f7f8f7` / `#d7ded8` / 5 px. Directive écrite : « le gros arrondi fait
générique ».

### 5.5 Autres composants

Héros à maille, rangées d'index numérotées, vignette-document (mini-page esquissée, survol
`rotate(-2.2deg)` + soulèvement), chips CCF, **pilule média** (`ccfMediaBtn` : logo + lien, trois
tailles `lg`/`xs`/`plain`, registre dupliqué dans `newsletter.py`), loader de page, kit de
révélations au défilement — tous décrits dans le skill `esthetique-ccf`.

---

## 6. Rédaction

### 6.1 Les trois lois

1. **Chaque affirmation porte un chiffre, un nom ou une date — ou elle saute.**
   « La couverture s'intensifie » → « la part des articles feux passe de 1 à 33 % en deux jours ».
2. **L'incertitude se déclare avec ses bornes, pas avec des adverbes.** « pourrait
   potentiellement » est interdit ; « n.s. après correction », « IC 95 % [x ; y] », « sous réserve
   de la fenêtre courte » sont la manière scientifique de douter.
3. **Corrélation ≠ causalité, dans la phrase même.** Jamais « les feux ont fait taire les
   militants » ; écrire « pendant l'épisode, la part des voix militantes tombe de X à Y % », et
   réserver l'interprétation causale à une phrase explicitement présentée comme une lecture.

**Aucun nombre écrit de mémoire, jamais** : tout chiffre publié vient d'une cellule calculée, et
une vérification par programme le confronte aux résultats.

### 6.2 Tics de prose interdits (structure)

- **Le pivot par négation** : « ce n'est pas X, c'est Y », « it's not X, it's Y ». Dis ce que la
  chose **est** ; le contraste se porte par les chiffres, pas par la syntaxe.
- **La règle de trois systématique** (« précis, sobre et rigoureux ») : varie les groupements.
- **Les parallélismes en miroir** de fin de section et les **chutes en aphorisme** (« X est le Y
  du Z »).
- **Les questions rhétoriques d'amorce** dans le corps (un *titre* de note peut poser la question
  de recherche ; les paragraphes n'en posent pas).
- **Les fragments dramatiques hachés** (« Un choc. Brutal. Inattendu. »).
- **L'annonce de plan** (« Voyons maintenant », « Let's dive in ») : la structure se voit par les
  titres.
- **Le tiret cadratin** : un par phrase au maximum, jamais la triple incise « qui signe la
  génération ». Préfère les deux-points, la parenthèse, ou deux phrases.

### 6.3 Vocabulaire à remplacer à vue

*Français* : pivot(al), « paysage » métaphorique, « au cœur de », « force est de constater »,
« véritable » intensif, « majeur » réflexe, « clé » adjectif, « riche », « crucial », « il convient
de noter », « en somme ». Copules : « constitue », « représente », « s'avère » quand « est » suffit.

*Anglais* : delve, landscape, tapestry, pivotal, robust, comprehensive, leverage, underscore,
crucial, notably, seamless, holistic, nuanced, fostering, showcasing, testament to, serves as
(→ is), features (→ has).

### 6.4 Contenu

- **Pas de méta-narration des évènements.** Quand des faits touchent des personnes (feux,
  évacuations), raconte **les faits** (« des communautés sont évacuées », « la Croix-Rouge est
  mobilisée »), jamais la fabrication du récit (« le récit s'organise autour de… »). Les mots
  « récit » et « story » appartiennent à l'analyse, pas au compte rendu.
- **Pas d'attribution vague** : « des experts estiment » → nomme (« le spécialiste des feux Mike
  Flannigan, Université de l'Alberta »), ou supprime.
- **Pas d'inflation d'importance** : « moment charnière », « tournant historique » ne s'écrivent
  que si une mesure les soutient.
- **Pas de conclusion positive générique** : une note se termine sur ses limites ou sur une
  implication concrète, jamais sur un vœu. « Défis et perspectives » est une section-formule
  interdite.
- **Pas de méta-langage de modèle** dans une surface publiée (« the provided text », « this
  article… ») — une garde le rejette, mais ne la teste pas.
- Gras : au plus un par paragraphe, sur la donnée, jamais sur l'opinion.
- Pas de listes à puces dans le corps analytique : la liste est pour les messages clés et les
  limites, la prose pour l'analyse.
- Une idée par paragraphe, l'idée en première phrase, la preuve ensuite ; longueurs de phrases
  variées (8 à 30 mots).
- Voix active, acteurs nommés en sujets ; le « nous » méthodologique est admis, le « je » jamais.
- **Section Limites obligatoire**, écrite contre soi-même : chaque limite dit ce qu'elle pourrait
  invalider, pas une formule de prudence.

### 6.5 Bilinguisme et chiffres

**Le français et l'anglais sont deux rédactions natives, pas une traduction** : idiomes, ordre des
arguments et ponctuation suivent chaque langue. Un anglicisme en français (« adresser un
problème ») ou un gallicisme en anglais disqualifie la page.

Français typographique : espace insécable (`&nbsp;`, jamais le caractère littéral) avant `; : ? %`,
virgule décimale. Anglais : point décimal, pas d'espace avant `%`. Toujours la base au premier
usage d'une mesure (« n = 155 », « sur 306 histoires ») ; p ajustés, jamais p bruts seuls.
Tous les horodatages affichés sont à **l'heure de Montréal** (un shim `Date.prototype` dans
`base.html` et `embed.html` force America/Toronto).

### 6.6 Le protocole de relecture (obligatoire avant livraison)

1. Rédiger **contre les tableaux de résultats**, aucun chiffre de tête.
2. **Audit anti-tics** en citant les occurrences trouvées.
3. Réécrire sans introduire de fait nouveau.
4. **Second passage dédié aux seuls patrons de structure** (pivot par négation, règle de trois,
   parallélismes).
5. **Audit par regex sur la page rendue** : incises doubles
   `[.;:!?]\s[^.;!?]*—[^.;!?]*—` et flèches hors `<svg>`/`title=`.

**Corollaire :** quand un tic est corrigé, corrige **les trois supports d'un coup** — le site, le
PDF (`docs/analyses/…`) et l'artifact — sinon ils divergent.

---

## 7. Les quinze invariants des livrables

Valables pour le site, les PDF, l'infolettre, les courriels, les cartes sociales et Bluesky.

1. **Bilinguisme natif**, jamais une traduction : deux rédactions distinctes par livrable.
2. **La marque est portée par le logo, pas par le mot** : pas de « · CCF » redondant ; les cartes
   sociales ne portent aucun titre, « le visuel parle seul ».
3. **Aucun chiffre écrit de mémoire** — toujours une cellule calculée ou une lecture en base.
4. **Sémantique de couleur constante** : vert forêt = gain/présence/défense · braise = recul/alerte.
5. **Le kicker en capitales espacées ouvre toute unité de contenu**, avec un marqueur graphique en
   tête (phare, glyphe de vue, ou ✦ par défaut).
6. **Couple typographique unique** : titres serif (Lora → Georgia en repli), corps sans (Archivo),
   prose longue Source Serif 4.
7. **L'encadré est pâle + filet fin + petit rayon** (voir 5.4).
8. **Toute entité qui a une fiche est hyperliée** vers l'observatoire, avec la même URL canonique
   partout : `?entity=<nom canonique>&ekind=PER|ORG&ewin=week` (préfixe `/fr/observatory` en FR).
9. **Chaque pièce déclare son type dès sa première ligne visible** (pastille d'édition, kicker
   « NOTE D'ANALYSE · Nº n · date », signature de fil).
10. **Le pied porte l'équipe et le domaine** : « L'équipe du Journal du climat — Alizée Pillod ·
    Antoine Lemor · Matthew Taylor », puis `ccf-project.ca`.
11. **Repli gracieux obligatoire** : aucun livrable ne casse sur une dépendance absente (la carte
    sociale retombe sur le cache puis sur le logo ; « le pouls ne casse jamais la lettre »).
12. **Emojis interdits** dans la prose scientifique ; registre fermé toléré sur Bluesky seulement.
13. **La flèche → est un langage de figure**, jamais de prose.
14. **Un seul jeu de fichiers de marque** alimente tous les livrables (voir 3.1).
15. **Ordre éditorial commun des livrables longs** : identification → titre → question ou lede →
    résumé exécutif → messages clés autoportants → analyse avec figures → limites → méthodes →
    signature.

---

## 8. La note d'analyse — le gabarit de référence

La note pilote (feux de forêt, juillet 2026) est le **modèle à généraliser**. Elle existe en quatre
artefacts : PDF une page et page web longue, chacun en français et en anglais.

### 8.1 Blocs nommés (plan de rédaction réutilisable tel quel)

**Le résumé CCF → Les points importants CCF → L'analyse CCF (+ Les figures CCF) → Le pouls CCF →
Les limites CCF → La lecture CCF (acteurs climatiques) → La méthode CCF.**

Composition : les deux premiers blocs en pleine largeur, tout le reste en deux colonnes avec les
figures à droite.

### 8.2 Squelette du PDF (une page Letter)

Masthead (lock-up paysage + kicker « NOTE D'ANALYSE · Nº n · DATE ») → titre déclaratif Lora 13 pt,
10-16 mots, **sans point d'interrogation** → « Question de la quinzaine — <question complète, 35-40
mots> » → résumé exécutif pleine largeur → messages clés → figures → limites → implications →
méthodes → pied.

### 8.3 Squelette de la page web

Héros (kicker au phare + h1 avec un `<em>` à dégradé + question + méta + deux boutons PDF +
retour) → **encart récit « Ce qui s'est passé »** (Source Serif, 150-170 mots, aucun chiffre
d'analyse — le seul bloc typographiquement différent, il donne le contexte humain avant l'analyse)
→ résumé exécutif → messages clés → analyse et figures → tableaux « Qui porte la parole » →
limites → méthode.

*Piège technique :* ne découpe jamais un `<em>` à dégradé en mots — `background-clip:text` est
invisible à travers des enfants `inline-block`. Le splitter de titre traite l'`<em>` comme **une**
unité `.w`.

### 8.4 Longueurs mesurées (le gabarit implicite)

PDF : 878 mots en français, 780 en anglais (résumé 174/153 · messages clés 178/148 · lecture pour
les acteurs 123/103 · limites 37/32 · méthodes 42/42). Page web : 2 192 / 1 923 mots, soit ~2,5 ×
le PDF. **Le français fait systématiquement 12 à 14 % de plus que l'anglais** — d'où la règle CSS
`html[lang=fr]` qui réduit le corps de 7,3 à 7,05 pt.

Bornes imposées à un rédacteur d'agent (plus serrées que le pilote, qui est la référence de
qualité) : titre 10-16 mots · résumé ≤ 90 mots · 3-4 points de ≤ 22 mots · analyse ≤ 140 mots ·
limites ≤ 60 mots.

### 8.5 Grammaire des légendes (formule fixe)

**[Figure n — ce qui est mesuré, en gras]** + (unité et mode de mesure) + fenêtres et n +
traitement (déduplication) + critère de sélection statistique + aide d'usage. La légende dit
toujours quel ton est le clair et quel ton est le foncé — c'est le seul endroit où la flèche est
permise hors étiquettes. Une légende de tableau porte une **lecture**, pas seulement une
définition. Les figures sont numérotées sur le web, pas dans le PDF.

### 8.6 Ce qui fait sa réussite (à reproduire)

Une seule couleur d'accent et une seule couleur de contradiction ; un titre déclaratif et apaisé
avec la question reléguée dessous ; chaque bloc signé par le logo ; la note **navigable** (21
entités hyperliées, tiroir de fiche ancré sur la date de clôture) ; un récit d'ouverture sans
statistique ; et surtout **un résultat négatif et une auto-correction publiés** — la crédibilité
vient de ce que la note se contredit elle-même avec des chiffres. Varie les formes de
visualisation : jamais deux fois la même dans une note.

---

## 9. Pièges vérifiés (ne pas les redécouvrir)

- **Cache CSS** : modifier un CSS sans bumper `?v=` ne change rien chez le visiteur.
- **Overlays** : un `transform` figé par une animation `forwards` casse `position:fixed` — les
  tiroirs doivent être reparentés vers `body` à l'ouverture (symptôme : « rien ne s'ouvre » sur
  iPhone).
- **Chaînes échappées** : `&eacute;` échappe aux remplacements littéraux ; les espaces insécables
  et apostrophes typographiques défont les `str.replace` naïfs.
- **Vues matérialisées** : un article annoté mais absent d'`article_frame_profiles` signifie une
  matview en retard — `REFRESH ... CONCURRENTLY`.
- **Nommage des acteurs** : les live-blogs donnent N titres pour une histoire (tronquer au premier
  `:` ou `;`) ; ECCC existe en trois graphies à agréger avant toute conclusion.
- **✦ n'est pas un emoji** (U+2726) : faux positif classique des audits.
- **Deux systèmes chromatiques coexistent** : la marque est bleu nuit + or, le site est forêt +
  teal + menthe. Le logo n'a jamais été reteinté ; ne « corrige » pas cela sans décision.

---

## 10. Tenir ce canon à jour

1. **Quand le code change, ce fichier change dans le même commit.** Une valeur citée ici doit
   rester trouvable à l'adresse indiquée.
2. **Ne duplique jamais une règle** : elle vit ici, le skill en donne le détail opératoire, la
   mémoire n'en garde qu'un pointeur d'une ligne.
3. **Copie synchronisée** dans le dépôt scientifique (`CCF-canadian-climate-framing/CLAUDE.md`) :
   elle porte un en-tête « copie générée — ne pas éditer ici ». Toute modification se fait ici et
   se recopie.
4. **En cas de doute, va lire le code**, pas ta mémoire de ce canon.
