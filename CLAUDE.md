<!-- COPIE GÉNÉRÉE — NE PAS ÉDITER ICI.
     Source unique : CCF-website (dépôt privé ccf-web), fichier CLAUDE.md à la racine.
     Toute modification se fait dans la source puis se recopie (canon, règle 10.3). -->

# CANON CCF — règles de maison, identité et charte

> **Ce fichier est la source d'autorité du projet CCF.** Il est chargé automatiquement dans
> chaque session. Lis-le en entier avant d'écrire une ligne de code, de prose ou de CSS.
> Il vaut pour le site, l'observatoire, les notes d'analyse, l'infolettre, les courriels, les
> cartes sociales, les publications Bluesky et le papier scientifique.
>
> **Version du canon : 1.1 — 2026-08-31.** Établi par audit du code réel (8 agents, 757 faits
> vérifiés). Chaque valeur porte son adresse : si le code a changé, **le code gagne** — corrige
> alors ce fichier dans la foulée.

## 0. Comment ce fichier s'utilise
<!-- ccf:acces founder -->

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

**Ce canon est servi aux collaborateurs par le serveur MCP, section par section.** Chaque titre
de niveau 2 porte un marqueur invisible en commentaire HTML — `<!-- ccf:acces tous -->` ou
`<!-- ccf:acces founder -->` — qui décide si la section part dans le brief d'un collaborateur
selon son tier. Les règles de maison (interdits, marque, visuel, rédaction, gabarits, pièges)
sont réservées au tier **fondation** : ce sont celles qui engagent notre nom. En ajoutant une
section, pose son marqueur ; sans marqueur, elle est traitée comme réservée.

**Ce canon dit ce que la maison écrit ; deux autres fichiers disent le reste, et ils ne le
répètent pas.** `documents/CHARTE.md` dit comment tout cela devient une page imprimée.
`documents/GUIDE_AGENT.md` et sa rédaction anglaise `GUIDE_AGENT.en.md` disent comment un agent
conversationnel MÈNE le travail avec un fondateur : quelle branche prendre selon la demande, quand
un dépôt se justifie et quand il est du bruit, quand demander une précision plutôt que deviner,
quand refuser. Le serveur MCP les sert au tier fondation sans qu'on les demande — l'abrégé du guide
dans le champ `instructions` du protocole, le guide entier dans `ccf_briefing`, avant ce canon
(`mcp-server/ccfmcp/guide.py`). Une règle qui vaut pour toutes les surfaces monte ici ; une règle
de conduite d'entretien reste là-bas.

---

## 1. Identité
<!-- ccf:acces tous -->

**Ce qu'est CCF.** L'observatoire du cadrage médiatique climatique canadien : une base annotée
(283 964 articles, 22 médias, 1978-2026, 9,9 M d'unités de deux phrases annotées sur une
grille de **65 catégories** par 128 classifieurs), un site public (ccf-project.ca), une chaîne de traitement continue qui l'alimente,
et un papier de méthode, publié dans Scientific Data (Nature Portfolio, 2026 ; DOI
10.1038/s41597-026-08330-9). Le produit est **scientifique**, pas militant.

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
<!-- ccf:acces founder -->

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
11. **Les noms des fournisseurs d'archives de presse (Eureka, Factiva, ProQuest, RefMedia) ne
    s'écrivent sur AUCUNE surface publique** — site, PDF, infolettre, courriels, réseaux, dépôts
    publics. On écrit « nos bases d'archives de presse » (demande du 31-08 : « on ne doit JAMAIS
    parler d'eureka factiva ou proquest. Ne l'écrit nul part » ; RefMedia rejoint la liste avec la
    quatrième base, le 31-08). Ils restent nommables dans le code privé et les panneaux admin.
12. **« pipeline » et « échelle » sont bannis de toutes les surfaces publiées**, dans les deux
    langues (demande du 31-08). On écrit « chaîne de traitement » / « la chaîne » en français,
    « processing chain » / « the chain » en anglais ; « à l'échelle de » se remplace par « sur »,
    « sur l'ensemble de ». Le mot pipeline reste permis dans le code et les noms de fichiers.

---

## 3. La marque
<!-- ccf:acces founder -->

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
<!-- ccf:acces founder -->

### 4.1 Où vit le CSS

Deux feuilles sur **toutes** les pages, dans cet ordre : `static/css/main.css` (3 435 lignes, la
source canonique) puis `atlas-shell.css` (la coquille du registre récent). Toute autre feuille est
ajoutée par sa page via `extra_css` : `home-concepts.css` (accueil publié, variante
`research-refined`), `about-atlas.css`, `team-atlas.css`, `contact-atlas.css`,
`database-atlas.css`, `services-newsletter.css`, `observatory-atlas.css`, `obs-rail.css` ;
Base et méthode charge en dernier `database-canon.css` (le jeu de composants `dbx`, il
« ferme la marche » sur les deux feuilles précédentes).

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

Quatre familles, **servies par nos serveurs** depuis le 25-09-2026 (`static/css/fonts.css` et
`static/fonts/`, régénérés par `scripts/vendor_fonts.py`, licences OFL à côté), `display=swap` ;
plus aucune requête vers Google Fonts (voir §9bis) :

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

## 4bis. Les courriels — le registre Atlas
<!-- ccf:acces founder -->

**Un courriel CCF est bâti comme une page du site : des pavés verts qui ouvrent, du texte clair
entre eux, et le pied Atlas pour fermer.** L'enveloppe partagée vit dans
`data-server/email_service.py` (`email_wrap` et ses briques `_manchette`, `_tete`, `_p`, `_etapes`,
`_valeur`, `_note`, `_signature`) ; `extraction/mcp_mail.py` en est le gabarit d'application. Une
lettre qui ouvre sur du blanc, ou qui empile des cartes arrondies, n'est pas de ce produit.

### 4bis.1 Le pavé de manchette
Fond `#12362d`, **aligné à gauche** et **encastré dans la gouttière** de 34 px — sur le site aucun
pavé n'est à bord perdu, ils font tous `width:min(1200px, calc(100% - 48px))`. Rayon 0, aucune
ombre, aucun dégradé : le halo `radial-gradient` du héros ne survit pas à Outlook, et un
`background-image` en échec laisse un fond blanc. Il porte, dans cet ordre : le **mât** (médaillon
40 px et kicker `#9bd2c1` en capitales lettrées `.22em` sur la même ligne, grammaire `.dbh__mast`),
le **titre** en serif 27 px blanc dont **un seul mot passe en menthe `#a6dac9`**, la **ligne
d'édition** en capitales `#8faea3`, le **bouton**, et un **filet de clôture** `#81b1a2` en bas à
droite sur 34 % de la largeur (signature `.dbh::after`).

### 4bis.2 L'en-tête de section — sur fond vert, avec son symbole
**Chaque section s'ouvre sur son propre pavé vert**, réduction du pavé de chapitre `.dbh`
(`database-page.css` l. 3190) : fond `#12362d`, padding `22px 26px 20px`, kicker `#9bd2c1` en
capitales lettrées `.15em` **précédé de son symbole**, titre serif 21 px blanc, lede `#bed0c9` en
serif 14 px, et le même filet de clôture à 34 %.

Le **symbole** vient du rail de l'observatoire, qui donne à chaque vue le sien : ◧ vue d'ensemble ·
❖ le Journal · 〜 le pouls · ◈ à travers le pays · ⇲ cascades · ▤ articles · ▥ cadres · ◐ émotions ·
▧ par média · ✎ méthode. Une section sans vue correspondante prend **✦**. Le phare vectoriel du
kicker (`.ccf-lh`) ne se transpose pas : un SVG inline ne survit pas à Gmail, et le canon §7.5 admet
le glyphe de vue ou ✦ comme marqueur de tête.

### 4bis.3 Le pied — celui du site
`.footer--atlas` (`atlas-shell.css` l. 447) : fond `#0b2922`, **filet menthe `#a6dac9` de 1 px en
tête**, la marque à gauche (médaillon 52 px, nom en serif blanc, baseline `#8faea3`), les liens en
**pavés bordés** `#23413a` à rayon 3 px, et le **dernier pavé pleine largeur sur fond menthe**
`#a6dac9`, encre `#12352c` en gras — c'est lui, le bouton du pied. Puis la note d'usage loyal
(`#79988d`), la signature de l'équipe et le millésime, séparés par des filets `#203e37`.

**La signature est celle de l'observatoire** : « L'équipe de l'observatoire CCF » / « The CCF
observatory team ». Le Journal du climat est une vue de l'observatoire, et sa signature appartient
à l'infolettre seule. Voir l'invariant nº 10.

### 4bis.4 Le bouton
Un seul par lettre, dans le pavé de manchette. Sur fond sombre il est **menthe** : fond `#a6dac9`,
encre `#12352c`, bord `1px solid #8abfad`, rayon 4 px, libellé sans 700 suivi de ✦. C'est la recette
du dernier lien du pied Atlas et du bouton d'abonnement du Journal. Le bouton de verre `.btn-lh` ne
se transpose pas : `backdrop-filter` n'existe pas en messagerie.

### 4bis.5 Le corps clair, entre les pavés
Repris des notes d'analyse : prose en **serif** 15 px interligne 1,75 `#24382e` ; encadré `#f2f7f3`
sur filet `#c9d9cc`, rayon 4 px, **réservé aux valeurs à recopier** ; note et mise en garde sous un
filet fin `#cfdccf`, en `#5c7166` ou en braise `#b0492f` ; étapes numérotées en rangées séparées d'un
filet, numéro en serif `#0a5c4a` — **la menthe tombe à 1,56:1 sur blanc et y devient illisible** ;
listes et échelles à plat, l'élément actif distingué par son kicker et son encre, jamais par un
aplat.

### 4bis.6 Les contraintes de messagerie qui expliquent le reste
· **Aucune police web ne se charge** — Gmail, Outlook et Yahoo retirent le `<link>` du `<head>`.
Écrire « Lora » ou « Archivo » dans un style en ligne est un défaut : on écrit les replis que le
canon §4.5 nomme, soit Georgia pour le display et la prose, Arial pour la sans.
· **Le fond des pavés est posé deux fois**, en propriété CSS **et** en attribut `bgcolor`, sans quoi
le mode sombre de Gmail repeint le fond et laisse un texte clair sur clair.
· **Les `rgba` sont aplatis**, qu'Outlook rend mal au-dessus d'un `bgcolor`. Sur `#12362d` : `.75`
donne `#81b1a2`, `.28` donne `#3b6459`, `.18` donne `#2d5449`. Sur `#0b2922` : `.15` donne `#23413a`,
`.13` donne `#203e37`.
· **Outlook réinitialise la police à chaque cellule**, ignore `display:flex` et `linear-gradient`.
Tout est en tables imbriquées, en aplats et en styles incorporés ; les classes de la feuille ne
servent que de repli aux gabarits pas encore migrés.

### 4bis.7 Le phare dans chaque en-tête
Chaque pavé de section porte le **médaillon du phare en 26 px**, aligné à droite, en vis-à-vis du
kicker. Le canon §5.1 veut le phare en tête de kicker ; en courriel il ne peut pas y être en SVG, et
une image de 13 px collée au texte se lit comme une puce sale. Il occupe donc la place que le
filigrane occupe sur les cartes du site (`.abt-mission__wm`) : la section porte la marque sans que
le kicker s'alourdisse.

### 4bis.8 Les liens — une seule couleur, et jamais d'adresse nue
**Une couleur de lien, la même partout** : le vert d'action `#0a5c4a` sur fond clair (7,95:1 sur
blanc), la menthe `#a6dac9` sur fond sombre (8,48:1 sur `#12362d`). Aucune couleur claire sur fond
clair, aucun bleu.

**Aucune adresse ne reste en texte nu.** Une URL ou une adresse de courriel posée hors d'une balise
`<a>` est détectée par Gmail, Apple Mail et Outlook, qui la repeignent de LEUR bleu — une couleur
qui n'est dans aucune palette de la maison. Toute adresse est donc enveloppée dans un `<a>` portant
sa couleur, et l'enveloppe pose la garde `<meta name="format-detection" content="telephone=no,
date=no,address=no,email=no">` plus la règle `a[x-apple-data-detectors]{color:inherit!important;…}`,
qu'iOS applique là où il ignore la balise. Une valeur qui n'est ni une URL ni une adresse (un
identifiant, un jeton, un mot de passe) reste du texte, mais reçoit sa couleur explicitement.

**Chaque mention du guide porte son lien.** Quand une lettre renvoie au guide de branchement, elle
donne l'adresse cliquable au même endroit, pas seulement dans le bouton de la manchette : un lecteur
qui parcourt la lettre par le milieu ne remonte pas au bouton.

### 4bis.9 Toute lettre part en deux parts
Le message est un `multipart/alternative` qui porte une part **texte** puis la part HTML, dans cet
ordre — le client retient la dernière qu'il sait rendre. La part texte se **dérive** du HTML
(`email_service.html_to_text`) plutôt que de s'écrire à part : deux rédactions divergeraient au
premier changement. Une lettre sans part texte n'a rien à montrer à un client en mode texte, et son
absence pèse dans les scores anti-pourriel.

### 4bis.10 Les listes ont deux niveaux
Une liste dont un item **annonce** ce qui suit — il se termine par deux-points, « Tout ce qu'Expert
permet, plus : » — met les items suivants **au second niveau** : en retrait, sous un tiret demi-cadratin
`–` en encre secondaire, et non sous la même ✦ que l'annonce. Les mettre au même rang fait lire
« tout ce qu'Expert permet » et « les points d'entrée d'administration » comme deux éléments
comparables, alors que le second est un exemple du premier. La brique `_dots` le détecte seule.

### 4bis.11 Le mode sombre des clients
Outlook et Gmail n'obéissent pas à `color-scheme:light` : ils **inversent** eux-mêmes ce qu'ils
jugent clair. On pilote donc l'inversion au lieu de la subir, par trois familles de sélecteurs,
parce qu'aucun client ne lit les mêmes : `@media (prefers-color-scheme: dark)` pour Apple Mail,
Gmail iOS et Thunderbird ; `[data-ogsc]` et `[data-ogsb]` pour Outlook mobile, qui réécrit le
document en préfixant ces attributs ; et les fonds posés en `bgcolor` sur les pavés, qu'aucun client
ne repeint — c'est pour cela que le vert des pavés survit partout.

**Le piège mesuré :** un fond de carte sombre trop clair fait DISPARAÎTRE les pavés. `#1a2124`
contre le vert `#12362d` ne donne que 1,24:1, et la lettre perd sa structure. La carte descend donc
à `#0d1113` (1,44:1) et le pavé reçoit en plus un filet `#2c5548`, comme sur le site. Les liens du
corps passent du vert d'action à la menthe, qui tient 9,3:1 sur ce fond.

**Les images portent leur description.** Une image en `alt=""` réserve sa place, et Outlook y dessine
un cadre vide quand il bloque le chargement — le phare des en-têtes apparaissait comme un carré blanc.
Chaque image porte son mot, sa cellule reprend le fond du pavé pour que le cadre s'y fonde, et le
style éteint bordure et soulignement.

**La marque GitHub** accompagne tout lien de dépôt, en **pastille** : la marque blanche sur un disque
plein du vert d'action (`github_mark_pastille.png`, 7,95:1). Elle a d'abord existé en deux tirages,
un d'encre et un blanc ; aucun ne tient dans un courriel, puisque le client décide lui-même du fond
et qu'Outlook en mode sombre effaçait le tirage d'encre. Le disque porte son propre contraste, quel
que soit ce qu'il y a derrière. Elle se pose **en table à deux cellules**, jamais en image inline :
Outlook pour Windows compose avec le moteur de Word, qui ignore `vertical-align` en pixels, et les
dimensions s'écrivent en attributs autant qu'en style.

**La lettre prend toute la largeur.** Pas de carte de 620 px posée sur une toile : deux fonds
empilés font flotter le message au milieu de sa fenêtre. Le papier de la lettre EST le fond du
message, et les pavés verts vont d'un bord à l'autre de la gouttière.

**Les dépôts vivent sous l'organisation** `github.com/ccf-organization` — les cinq y ont été
transférés le 31-08-2026, et les anciennes adresses `antoinelemor/…` ne font plus que rediriger.
Attention en cherchant : une URL coupée par la concaténation implicite de Python échappe à un
remplacement littéral, et `antoinelemor.github.io` est le site personnel, qui ne se touche pas.

### 4bis.12 L'indicateur — une piste, un segment, un chiffre
Un score sur 100 s'affiche par une **piste fine à l'encre pâle**, le **segment atteint** en couleur
pleine, et la **valeur en chiffres** à droite. C'est le langage des figures des notes d'analyse
(`.btrack` / `.bseg` / `.bvals`), et il ne coûte **aucune image** : deux cellules de table peintes,
que tous les clients savent rendre. La sémantique des teintes ne bouge pas (§4.3) : la forêt dit la
présence et l'influence, la braise dit la contestation et le recul. Un score non nul garde un
segment d'au moins 2 % — « presque rien » n'est pas « rien ».

Ce qu'il remplace : dix images de phare par indicateur, n allumées sur dix. Elles disparaissaient
entièrement dès qu'un client bloquait les images, elles demandaient de compter, et leur pas de dix
points écrasait l'écart entre 31 et 39. Quarante requêtes HTTP pour un podium.

**Les chiffres ont leur police.** Le canon §4.5 réserve `--font-mono` (Space Grotesk, qui n'est pas
une chasse fixe) aux dates, compteurs, axes et données tabulaires. En courriel on écrit son repli,
`'Space Grotesk', 'Helvetica Neue', Helvetica, Arial, sans-serif`, avec `font-variant-numeric:
tabular-nums` pour que les colonnes de chiffres s'alignent d'une ligne à l'autre. Un compteur n'est
ni un titre (Georgia) ni un jeton : la chasse fixe reste aux **codes et aux clés**, où il faut
distinguer 0 de O.

### 4bis.13 Les blocs de contenu
Les briques qui portent le contenu suivent les mêmes règles que le squelette.

**L'étiquette d'un bloc est un kicker**, donc elle porte son marqueur : ✦ par défaut, ou le glyphe
de sa vue. Une ligne de capitales sans marqueur n'est pas un kicker (invariant nº 5).

**Le pour-cent prend son espace insécable en français**, et le libellé d'un cadre prend la couleur
de son cadre : c'est l'information, pas la légende.

**Les noms comptés s'accordent.** « 1 article · 1 média », jamais « 1 articles · 1 médias ». Quand
le nombre vient d'un texte produit par un modèle, la consigne d'accord se pose **dans le prompt** :
le gabarit ne peut pas corriger une phrase qu'il n'écrit pas.

**Une phrase commence par une capitale**, y compris un sous-titre de section de trois mots.

**Le bouton d'un bloc** est l'aplat plein du registre (§4bis.4), jamais une pilule à filet pâle et
rayon 999 px, qui a la forme d'un bandeau de consentement. Un médaillon de 13 px devant son libellé
ne se lit pas et laisse un cadre vide quand les images sont bloquées : ✦ le remplace.

**Le piège des chaînes échappées** (canon §9) : une chaîne qui traverse `esc()` voit son `&`
réécrit, et l'entité `&nbsp;` s'y affiche alors en toutes lettres. Dans ces chaînes — libellés,
titres, contenus — l'insécable s'écrit **en caractère** (U+00A0) ; l'entité reste la règle dans le
HTML construit à la main, qui ne passe jamais par `esc()`. Le contrôle se fait sur le rendu, en
cherchant `&amp;nbsp;`.

**La matière d'un prompt peut être dans une autre langue que la lettre.** Quand les faits fournis au
modèle sont en anglais et la sortie en français, la consigne doit interdire explicitement de
recopier un fragment de la matière : sans cela « lean toward contesting » traverse jusqu'au lecteur.

### 4bis.14 Les encarts et les listes d'acteurs
**Une liste d'acteurs est une suite de RANGÉES, pas une grille de cartes.** Six cartes bordées
empilées font un tableau de bord ; le site aligne des rangées d'index (`.svc-idx`) séparées d'un
filet fin, et c'est ce qui donne à une liste son allure de page. Le rang s'écrit en **filigrane** —
un chiffre serif de 30 px à l'encre pâle `#c9d9cc`, dans sa propre colonne — jamais en pastille
ronde pleine collée au nom. Le nom de l'acteur est un titre, donc en serif.

**Une lettre n'a qu'une façon de présenter un acteur.** Podium, voix par rôle, classement : la même
rangée partout.

**L'encart de résumé est celui des notes d'analyse** (`.anz-story`) : fond `#f2f7f3`, filet
`#c9d9cc`, rayon 5 px, prose en serif, et son **kicker À L'INTÉRIEUR** du bloc, en capitales
espacées vertes précédées de ✦. Un intitulé posé dehors, en gris de méta, fait lire une étiquette
puis une boîte au lieu d'un bloc. La variante d'alerte teinte en braise (`#fbf3ef` sur `#e2c9bd`).

**Un badge de source suit le canon §5.4** : filet fin, petit rayon, teintes de la maison. Le bleu
`#46587a` et sa pilule à rayon 99 px n'appartiennent à aucune palette CCF.

### 4bis.15 La prose et les chiffres
La section 6 s'applique sans aménagement, et l'audit par regex (§6.6) se fait sur le courriel
**rendu**, tous les cas joués : chaque palier, chaque langue, compte neuf et compte existant. Les
chiffres viennent de `email_service.corpus_stats()`, qui lit `annotation_rollup` ; son repli figé ne
doit jamais être ce qui part chez le destinataire.

**Le guide se lit dans les deux langues.** La page de branchement vit à deux adresses,
`/account/connect` et `/fr/compte/brancher` ; chacune porte dans sa barre du haut un lien vers
l'autre, au même gabarit et à la même hauteur que les autres boutons, avec le nom de la langue
**en toutes lettres** (interdit nº 9) et les attributs `lang` et `hreflang`. Un lecteur arrivé par
le courriel anglais doit pouvoir passer au français sans repartir de l'accueil.

**Aucune plateforme n'est mise en avant.** Le serveur MCP se raccorde à sept applications, que la
page de branchement traite à égalité : Claude, ChatGPT, Le Chat et Gemini pour la conversation,
Claude Code, Cursor et VS Code pour le développement. Un courriel qui décrit les gestes « dans
Claude » et renvoie les autres à un « suivent la même logique » choisit pour le lecteur. Les étapes
s'écrivent donc au vocabulaire commun — réglages, connecteurs, connecteur personnalisé, adresse —
et la lettre nomme les plateformes ensemble, jamais l'une devant les autres. Cela vaut pour toute
surface publiée, pas seulement les courriels.

**Le contenu dit d'abord ce qu'il n'y a pas à faire.** Depuis OAuth 2.1 (`sql/mcp_oauth.sql`,
`mcp-server/ccfmcp/oauth.py`), un connecteur web se raccorde AVEC LE COMPTE : l'écran de consentement
demande l'identifiant, le mot de passe et le code à six chiffres, jamais le jeton. Une lettre d'accès
ouvre donc sur « aucun jeton à manipuler », donne les quatre gestes de la page de branchement
(`data-server/templates/connect.html`, constantes `ETAPES`, `CONNEXION`, `ESSAI`) **mot pour mot**,
et ne place le jeton qu'en avant-dernier, pour le terminal et les éditeurs. Le mot « OAuth »
n'apparaît nulle part : la page ne l'écrit jamais.

---

## 4ter. Les documents — la flotte imprimée
<!-- ccf:acces founder -->
**Tout ce qui se produit sous notre nom hors articles scientifiques passe par la flotte de
`documents/`, et la règle en est `documents/CHARTE.md`.** Fiches, notes sur commande, guides,
rapports, demandes de financement, ententes, communiqués : dix-neuf gabarits rangés en cinq
familles, déclarés dans `documents/catalogue.py`, composés par `documents/build.py`.

**Deux chaînes, et le choix ne se discute pas au cas par cas.** La chaîne LaTeX
(`documents/latex/ccfdoc.cls`, XeLaTeX) produit ce que nous **diffusons** : personne d'autre que
nous n'y écrit, le rendu est fidèle et reproductible hors ligne. La chaîne Word
(`documents/word/ccf-reference-{fr,en}.docx`, posés par `construire_reference.py`) produit ce que
nous **co-rédigeons** : un bailleur impose son formulaire, une collègue révise dans son traitement
de texte. Un manuscrit circule en Word et sort en PDF LaTeX ; le Word n'est jamais le livrable
final d'une pièce diffusée sous notre nom. Les deux branches portent la même hiérarchie — parties,
sections numérotées sur trois niveaux, annexes, sommaire ; côté Word les numéros viennent d'une
liste liée au style (jamais tapés) et le sommaire est un champ que **F9** remplit, Word ne
calculant aucun champ à l'ouverture d'un fichier écrit par programme. Les quatre formes ont leur
gabarit vide dans les deux langues (`documents/word/gabarits/`), et ce que Word ne sait pas
reproduire est écrit dans `documents/word/README.md`.

**La note d'analyse garde sa chaîne** (HTML puis Chrome, `docs/analyses/…/build_pdf.py`,
gabarit du §8) : son égaliseur de colonnes et son ajustement une-page sont calibrés au centième.

Ce que la flotte a ajouté au dossier de marque, parce que les documents en avaient besoin :
`ccf_paysage_ondark_{fr,en}.svg` et `ccf_icone_ondark.svg` — le lock-up et le médaillon en
**knockout pour fond vert** (mot-symbole `#F5F7F8`, contour et baseline menthe, filet ambre
conservé), qui comblent le manque signalé au §3.5 ; et `ccf_lh_{vert,menthe,braise}.svg`, le phare
du kicker gelé pour l'imprimé, faisceaux à l'opacité `.45` que `main.css` leur donne sous
`prefers-reduced-motion`. Les documents parlent le vert Atlas `#12362d`, pas le bleu nuit de la
bannière, dont le fond est cuit dans le fichier et ferait tache sur un bandeau vert.

**Trois pièges vérifiés, qui ne se redécouvrent pas :** les quatre familles de polices sont
**vendorées** sous OFL dans `documents/polices/` et chargées par chemin, sans installation —
la chaîne HTML de la note, elle, charge Google Fonts au rendu et produit un PDF hors charte sans
erreur si le réseau manque. Les logos sont **gelés** en PDF vectoriel dans `documents/marque/`,
avec Avenir Next embarqué en sous-ensemble : régénérés sur une machine sans cette police, ils
sortiraient hors charte en silence. Et **✦ n'existe dans aucune des quatre familles** (ni ◧ ❖ 〜 ◈
⇲ ▤ ▥ ◐ ▧ ✎) : sur le web le navigateur retombe sur une police système, en LaTeX le glyphe sort
blanc — la classe les route vers DejaVu Sans. Aucune formule mathématique, pas même `$\cdot$` :
une seule fait entrer Computer Modern dans le PDF.

**La flotte est branchée au serveur MCP au palier fondation** (31-08). L'outil `ccf_document`
suit les trois temps de la charte : catalogue, fiche de commande, document. C'est le **premier outil
qui a écrit** — `ccf_courriel` et `ccf_projet` écrivent aussi depuis —
et `readOnlyHint` a donc cessé d'être une constante de la boucle d'enregistrement pour
devenir le défaut du registre. `mcp-server/ccfmcp/documents.py` charge `catalogue.py` et `build.py`
**par chemin**, les relit à chaud, et compose dans un fil dédié à une place — hors du fil
d'écoulement de la file, qui est unique et sériel — sous une échéance dure de 45 s par passe. La
restitution passe par un **lien** : un PDF en base64 dépasse le plafond de 145 000 caractères. Deux
routes le servent, `/mcp/document/<ref>` par jeton porteur et `/account/documents/<ref>` par session
membre ; les fondateurs retrouvent leurs pièces dans une section de leur espace membre. Table
`mcp_documents` (`sql/mcp_documents.sql`), fichiers dans `var/mcp_documents/`, trente jours.

---

## 5. Les composants signature
<!-- ccf:acces founder -->

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

### 5.6 Base et méthode — le registre `dbx` (database-canon.css, 31-08)

Sept briques, et rien d'autre : `.dbh` (pavé de chapitre), `.dbx-lead` (chapô), `.dbx-idx`
(séquence numérotée), `.dbx-grid` (grille à filets), `.dbx-note` (encadré), `.dbx-desk`
(pupitre de démonstration), `.dbx-fig` (figure). Règles posées par retours d'Antoine :

- **Le pavé** : le médaillon animé (68 px) et le kicker « Chapitre n » partagent UNE ligne,
  centrés verticalement l'un sur l'autre (`.dbh__mast`, db_hero.html).
- **Au-dessus de 940 px, la pile devient une rangée** — jamais une colonne ferrée à gauche qui
  laisse la moitié droite vide : les `.dbx-idx__r` en grille numéro · titre+méta · description ·
  ✦ (géométrie des rangées d'index de Services) ; les `.dbx-note` à titre en deux colonnes
  titre-au-phare | prose, `width:fit-content`, marge droite habitée par un ✦ filigrane ; les
  `.dbx-lead` à lede en deux colonnes, la dernière ligne du lede posée sur celle du titre.
- **La frise des chapitres** (db_trail.html) : six pastilles toujours visibles, états
  parcouru ✓ / courant / à venir ; **le cap suivant** (`.dbnext`, db_next_fab.html) : pilule
  SOMBRE du dock de bord (fond `rgba(18,54,45,.94)`, filet menthe — jamais le vert d'action
  clair), reparentée dans `#ccfEdgeActions` pour qu'aucun ancêtre transformé ne piège son
  `position:fixed` ; à droite du beacon, à sa hauteur, elle mène d'étape en étape puis à
  l'observatoire. Les encarts composés se centrent horizontalement (`margin-inline:auto`).
- **Le tableau des sources** (db_view_sources.html) : rendu serveur, sous-sections conservées
  (nationaux, régionaux par langue) et **chaque sous-section rangée par volume croissant** ;
  la scène — tri, cascade des rangées, remplissage des jauges — ne se joue qu'à l'ENTRÉE du
  tableau dans le cadre, sinon le visiteur n'en voit jamais le mouvement ; rangée entière
  cliquable vers la fiche média, en-têtes de colonnes triables (`aria-sort` tenu).
- **Les panneaux** (dimensions et lectures) : en-tête CENTRÉ — kicker, titre, sous-titre et
  aide au clic —, et une navigation de retour qui NOMME sa destination (« Revenir aux six
  dimensions » / « Revenir aux quatre lectures »), en tête ET en pied, **centrée elle aussi**
  (ferrée à gauche jusqu'au 01-09 : seule à son bord sous un en-tête entièrement centré, elle
  partait de son côté). Piège : une règle générique de `database-page.css` force `text-align:left` et
  `max-width:26ch` sur `.dmp__title` et `.category-section__title` — il faut la contrer
  explicitement dans le panneau.
- **Les grilles ouvrent sur un chapô, jamais un kicker orphelin** (`.dgx-lead` : kicker,
  titre déclaratif, invitation), centré sur la grille qu'il annonce.
- **Le papier technique** : l'encart `.dbx-paper` (kicker au phare, titre, lede, deux actions
  `.dbx-btn` à droite) — jamais la vieille carte à boutons flottants.

---

## 6. Rédaction
<!-- ccf:acces founder -->

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
- **L'antithèse sous toutes ses formes**, et pas seulement le pivot par négation : « il y a un
  prix et une raison », « ce choix se paie et s'assume », « d'un côté… de l'autre », « la
  contrepartie… en échange ». Poser deux termes en balance est le réflexe le plus visible de la
  prose générée. Écris la chose, puis la suivante, sans les mettre face à face.
- **La coordination « , et »** : « Vous posez une question, et l'assistant répond », « Votre accès
  est en lecture seule, et la base refuse toute écriture ». Ce patron enchaîne deux propositions
  complètes par une virgule suivie de « et », et il revient à chaque paragraphe dès qu'on n'y prend
  pas garde. Coupe en deux phrases, ou remplace par un point-virgule, un deux-points, ou rien.
  Le « et » reste légitime **sans** virgule (« deux minutes et aucune ligne de commande ») et en
  fin d'énumération (« le corpus, l'observatoire et le code »).
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

*Les deux langues* (interdit absolu nº 12) : « pipeline » (dire « chaîne de traitement » /
« processing chain ») et « échelle » (« à l'échelle du corpus » se dit « sur le corpus entier »).

### 6.4 Contenu

- **Les étapes méthodologiques accomplies se racontent au passé.** « Nos étapes méthodologiques
  sont présentées ci-dessous dans l'ordre où elles ont été mises en œuvre » — jamais « dans
  l'ordre où elles se produisent » quand elles ont déjà eu lieu. Le présent est réservé à ce qui
  tourne réellement chaque jour (formulation d'Antoine, 31-08).
- **Les titres de section disent la méthode, directement** : « Notre méthode, en bref » /
  « Our method, in a nutshell », « Ce que notre méthode a produit, de 1978 à aujourd'hui ».
  Registre possessif et descriptif ; jamais d'aphorisme (« Tout ce que l'observatoire sait, il
  l'a appris des journalistes » : rejeté), jamais d'image (« Une même chaîne lit l'archive et
  l'actualité du matin » : rejeté), jamais de pivot par négation ni de « : » à effet.
- **L'extraction d'entités relève TROIS familles : personnes, organisations ET LIEUX.**
  Toute énumération qui n'en cite que deux est fausse (31-08 : « il manque les lieux »).
  Mesuré en base le 31-08-2026 : 2 201 586 personnes, 2 211 194 organisations,
  2 543 476 lieux — les lieux sont la famille la plus nombreuse. Exception légitime : le
  pouls médiatique ne classe au palmarès que les personnes et les organisations.
- **La grille compte SOIXANTE-CINQ catégories, et rien d'autre ne fait autorité que le
  codebook du dépôt** (`CCF-canadian-climate-framing/paper/CCF_Methodology/Publication/
  code_package/CODEBOOK.md`, miroir de la table supplémentaire S3). C'est le nombre de
  colonnes d'annotation de `CCF_processed_data`, le nombre de lignes de la table des paliers,
  et le nombre que le papier écrit partout. `config.ANNOTATION_CATEGORIES` en dérive et se
  sert à tout gabarit par le processeur de contexte de `app.py` : `categories|length` est la
  SEULE façon d'écrire ce nombre sur une surface publiée.
  *Corrigé le 20-09-2026 :* la liste en portait 59, soit 56 catégories réelles plus les trois
  familles d'entités nommées qui n'en sont pas. Neuf catégories manquaient, dont tout le cadre
  environnemental, que l'observatoire colorait pourtant déjà. Accueil et « à propos »
  annonçaient « 65+ », l'accueil « 120+ modèles » pour 128.
- **La reconnaissance d'entités n'est PAS une catégorie d'annotation.** Personnes,
  organisations et lieux se comptent à part (`config.NER_FAMILIES`), comme le papier les
  compte à part : « 65 catégories + NER ». Les additionner est l'erreur qui a produit le 59.
- **Le nombre de catégories s'écrit « une soixantaine » en PROSE** (31-08 : « ailleurs on a
  tendance à dire plus »), avec le nombre exact conservé dans les rangées de chiffres, les
  kickers et les méta — c'est de la donnée. La formule reste dérivée : une garde Jinja
  bascule sur la valeur exacte si `categories|length` sort de la fourchette 55-69.
- **Les valeurs publiées du papier et du dépôt vivent dans `config.CCF_PAPER`** et se servent
  aux gabarits sous le nom `paper` : 128 classifieurs, paliers A/B/C (27/21/17), F1 macro
  agrégé 0,866, moyenne par catégorie 0,773, AC1 de Gwet 0,894, kappa 0,596, alpha 0,698,
  1 000 phrases d'étalon-or, 4 000 d'entraînement, version 2.1.0 du dépôt et ses DOI, et le
  DOI de l'article publié (`paper.doi_paper`, Scientific Data, 2026) — **toute surface qui
  cite le papier pointe ce DOI**, jamais le PDF de `static/assets/pdf/` ni le préprint
  Research Square (publication du 24-09-2026).
  **Ces chiffres décrivent le dépôt GELÉ** : les compteurs d'articles et d'unités du site
  restent ceux de `obs`, lus en base et toujours plus élevés. Ne jamais substituer l'un à
  l'autre.
- **L'annotation manuelle a un fait établi** (31-08) : l'annotatrice experte Alizée{NB}Pillod a
  annoté elle-même, à la main, les phrases d'entraînement ; une deuxième personne a ensuite codé
  un échantillon à l'aveugle (accord inter-annotateurs). Aucune surface ne doit écrire que « les
  membres du projet » ont annoté « sous sa direction ».
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
<!-- ccf:acces founder -->

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
8. **Toute entité qui a une fiche est hyperliée**, avec la même URL canonique partout :
   `?entity=<nom canonique>&ekind=PER|ORG&ewin=week` (préfixe `/fr/observatory` en FR). C'est
   l'adresse des surfaces publiées — vitrine, infolettre, notes, courriels — et de tout tableau
   exporté, qu'un tableur doit savoir ouvrir. **L'explorateur, lui, ouvre la fiche chez lui** :
   `Fiche.entity` (`data-server/explorer/js/fiche.js`) la compose dans le tiroir depuis
   `/api/live/pulse-entity`, et toute vue qui nomme une personne ou une organisation pose les
   attributs de `Fiche.entAttrs` — un seul point pour tout le produit. Un chercheur qui suit un
   nom ne perd ni sa session, ni sa liste, ni ses filtres, et la fiche reste tenue par le palier
   du compte (`analyst`) et par le caviardage des textes hors budget.
9. **Chaque pièce déclare son type dès sa première ligne visible** (pastille d'édition, kicker
   « NOTE D'ANALYSE · Nº n · date », signature de fil).
10. **Le pied porte l'équipe et le domaine**, puis `ccf-project.ca`. La signature suit le
    livrable : « L'équipe du **Journal du climat** » pour l'infolettre et les surfaces du Journal ;
    « L'équipe de l'**observatoire CCF** » pour tout le reste — courriels d'accès et de compte,
    surfaces du serveur de données. Le Journal est une vue de l'observatoire, pas l'inverse. Les
    trois noms suivent toujours : Alizée Pillod · Antoine Lemor · Matthew Taylor.
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
<!-- ccf:acces founder -->

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
<!-- ccf:acces founder -->

- **Cache CSS** : modifier un CSS sans bumper `?v=` ne change rien chez le visiteur.
- **Overlays** : un `transform` figé par une animation `forwards` casse `position:fixed` — les
  tiroirs doivent être reparentés vers `body` à l'ouverture (symptôme : « rien ne s'ouvre » sur
  iPhone).
- **Chaînes échappées** : `&eacute;` échappe aux remplacements littéraux ; les espaces insécables
  et apostrophes typographiques défont les `str.replace` naïfs.
- **Vues matérialisées** : un article annoté mais absent d'`article_frame_profiles` signifie une
  matview en retard — `REFRESH ... CONCURRENTLY`.
- **La clef d'évènement est une clef de CONTENU** (sha1 des cinq plus petits `doc_id`,
  `data-server/extraction/events_pipeline.py`) : une recomposition du cluster la change, et le
  pipeline re-clé alors les artefacts par recouvrement (liste des tables du « report par
  recouvrement »). Toute mémoire clée sur `event_key` doit figurer dans cette liste ET porter
  son jeu d'articles — `journal_daily_pick.doc_ids`, `live_data._same_story` (même histoire si
  la moitié du plus petit jeu est partagée). Sans cela l'anti-répétition ne reconnaît plus une
  histoire : le 22-09, l'UE-Canada avait fait la une cinq fois en six jours sous trois clefs.
- **Nommage des acteurs** : les live-blogs donnent N titres pour une histoire (tronquer au premier
  `:` ou `;`) ; ECCC existe en trois graphies à agréger avant toute conclusion.
- **Une scène animée se RÉDUIT sur téléphone, elle ne se recompose pas.** Les schémas de
  base et méthode (`.dmp-stage`) placent leurs pièces en absolu et tracent leurs trajectoires
  dans un `viewBox` : les repasser en grille sous 640 px cassait le positionnement, et les
  flèches disparaissaient avec la chorégraphie. La scène garde sa composition de conception
  (880 × 320) et reçoit un `transform: scale()` calculé — classe `is-fit`, variables `--fit`,
  `--fit-w`, `--fit-h`. Deux pièges tenus : une scène en panneau fermé mesure 0 (un rapport nul
  l'écraserait), et l'observateur de taille se pose sur le PARENT, jamais sur la scène dont on
  fixe la hauteur — sans quoi il boucle et le navigateur coupe ses notifications.
- **✦ n'est pas un emoji** (U+2726) : faux positif classique des audits.
- **Deux systèmes chromatiques coexistent** : la marque est bleu nuit + or, le site est forêt +
  teal + menthe. Le logo n'a jamais été reteinté ; ne « corrige » pas cela sans décision.

---

## 9bis. Confidentialité et conformité
<!-- ccf:acces founder -->
**La politique de confidentialité est une promesse que le code tient.** Elle vit à `/privacy` et
`/fr/confidentialite` (`templates/privacy.html`, `templates/fr/privacy.html`), versionnée dans
`config.CCF_IDENTITE` (version, date, responsable, adresse postale). Toute nouvelle collecte, tout
nouveau fournisseur, toute nouvelle durée se reporte dans les deux rédactions, avec un changement de
version annoncé (Loi 25, art. 8.2). Le dossier interne est `docs/conformite/` (registre des
incidents, évaluations des facteurs relatifs à la vie privée, délégation du responsable).

**Le site public ne pose aucun témoin et ne contacte aucun tiers.** C'est ce qui le dispense d'un
bandeau de consentement ; une seule exception le ferait perdre. Polices, ECharts et D3 sont servis
d'ici (`static/fonts/`, `static/vendor/`, liés par symlinks dans `data-server/static/` et
`data-server/explorer/`) ; les portraits Wikimedia passent par `/api/portrait` (`portraits.py`,
`live_data` réécrit leurs adresses) parce que Wikimedia pose des témoins tiers. Seules les vignettes
d'articles restent chargées chez les médias (droit d'auteur : nous n'en gardons pas de copie pour le
site), et la politique le dit. **Ne réintroduis ni CDN, ni police distante, ni outil d'audience, ni
intégration tierce** sans passer d'abord par la politique et, s'il faut un consentement, par un
bandeau au registre Atlas. Deux en-têtes tiennent cette promesse face à Cloudflare, et ne se
retirent pas : `Cache-Control: no-transform` sur tout HTML (sinon Cloudflare y injecte sa mesure
d'audience) et `NEL: {"max_age":0}`, posé par Caddy sur les deux domaines (sinon Cloudflare fait
envoyer par les navigateurs leurs erreurs réseau à `a.nel.cloudflare.com` ; vérifié le 25-09 :
Cloudflare n'ajoute plus alors ni `NEL` ni `Report-To`).

**Le nombre de visites sur 30 jours** (`visites.py`, LaunchAgent `com.ccf-web.visites`, toutes
les heures) remplace le compteur en direct (retour d'Antoine le 25-09 : « le compteur en simultané
ne dépassera que rarement 1 »). Il se compte dans le journal de Caddy, sans l'adresse IP, avec la
définition de Cloudflare (une page ouverte depuis un autre site, un lien ou un favori ; la
navigation interne ne compte pas) ; comme chez Cloudflare, seuls les robots qui se déclarent sont
retirés (choix d'Antoine, 25-09 : 10 458 visites sur 30 jours, dont environ les deux tiers viennent
de programmes qui se font passer pour des navigateurs ; exiger `Sec-Fetch-Dest: document` les
écarterait). Seuls des totaux par jour sont gardés (`var/visites.json`, 400 jours) ; le serveur les
rend sous le titre de la marque (`.nav__visites`, téléphone et ≥ 1161 px) et dans le pied, sans
aucun script chez le visiteur. Un jeton d'API Cloudflare (Analytics:Read) permettrait d'afficher
à la place les chiffres de leur tableau de bord.

**Les formulaires publics passent par `frein.py`** (cinq envois par dix minutes et par IP, en
mémoire, empreinte salée) : contact et infolettre.

**Chaque formulaire porte l'avis de collecte** `includes/collecte_avis.html` (`avis_type`
infolettre ou contact, `avis_cls` = le petit texte du formulaire), un champ piège `.ccf-hp` et,
pour l'infolettre, son `data-source`. Changer le texte de l'avis infolettre, c'est changer
`config.NL_CONSENT_VERSION` (preuve du consentement, LCAP art. 13).

**L'infolettre obéit à la Loi canadienne anti-pourriel.** Double confirmation par BOUTON (un GET
n'abonne, ne désabonne ni ne modifie rien : les filtres de messagerie ouvrent les liens) ; réponse
du formulaire identique quel que soit l'état de l'adresse ; changement de préférences confirmé
depuis la boîte ; `List-Unsubscribe` + `List-Unsubscribe-Post` sur chaque lettre ; adresse postale,
courriel et politique dans chaque pied (`email_service._mentions_legales`, `newsletter._footer`).
L'adresse postale est « à venir » depuis le 25-09 : `CCF_IDENTITE['adresse_lignes']` est vide et
les pieds l'omettent ; tant qu'elle manque, la LCAP n'est pas entièrement remplie ;
aucune réactivation depuis le panneau. Les durées (demande non confirmée 30 j, preuve de retrait
3 ans, envois 12 mois, journaux 30 j et 12 mois) sont appliquées chaque nuit par
`scripts/purge_retention.py` (LaunchAgent `com.ccf-web.retention`, 04 h 20).

**Les portes de la plateforme** (chantier du 25-09-2026, tests : `data-server/tests/
test_securite_portes.py`). Toute route qui vérifie un mot de passe ou un code passe par
`data-server/garde.py` : un frein par adresse en mémoire, et un frein par COMPTE en base
(`auth_echecs`, 20 mots de passe erronés par heure, 5 codes par quart d'heure et 20 par jour),
que le serveur MCP charge par son chemin pour compter les mêmes échecs. Un secret se garde par
`data-server/coffre.py` : secrets TOTP chiffrés (`CCF_COFFRE_CLE` dans `data-server/.env`, à
sauvegarder avec lui, jamais avec la base), jetons à usage unique (réinitialisation, codes et
jetons OAuth) en SHA-256, cookie de session chiffré et `Secure`. Un compte naît avec un LIEN
D'ACTIVATION (`db.create_user`, sept jours, usage unique), jamais avec un mot de passe envoyé par
courriel. Une route qui touche au compte relit la clé en base (vivante, ordinaire, non éphémère)
au lieu de se fier à sa signature ; un geste sensible redemande le mot de passe et répond 403, pas
401 (l'explorateur ferme la session sur tout 401). En base, seuls `ccf_app`, `antoine` et les
paliers MCP se connectent ; les fonctions `SECURITY DEFINER` ne s'exécutent plus par `PUBLIC`
(`sql/securite_plateforme.sql`, à rejouer après `sql/mcp_roles.sql`). Les blocs Caddy du CCF
renvoient vers l'adresse publique toute connexion qui n'arrive pas du tunnel : `Cf-Connecting-Ip`
n'est fiable qu'à cette condition.

---

## 10. Tenir ce canon à jour
<!-- ccf:acces founder -->

1. **Quand le code change, ce fichier change dans le même commit.** Une valeur citée ici doit
   rester trouvable à l'adresse indiquée.
2. **Ne duplique jamais une règle** : elle vit ici, le skill en donne le détail opératoire, la
   mémoire n'en garde qu'un pointeur d'une ligne.
3. **Copie synchronisée** dans le dépôt scientifique (`CCF-canadian-climate-framing/CLAUDE.md`) :
   elle porte un en-tête « copie générée — ne pas éditer ici ». Toute modification se fait ici et
   se recopie.
4. **En cas de doute, va lire le code**, pas ta mémoire de ce canon.
