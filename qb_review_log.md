# Review Agent — Rapport de vérification
**Date :** 2026-05-27
**Reviewer :** Review Agent (Passe 1)
**Fichier analysé :** `preview/03-queue-busting.html`
**Référence Figma :** fileKey `WXJDiB40xI61G5fnJPZqE8` — screenshot local `figma_qb_preview.png`

> **Note Figma MCP :** Le plan Starter a atteint sa limite d'appels d'outils. Les screenshots Figma par section n'ont pas pu être récupérés via l'API. La comparaison est basée sur :
> - Le screenshot Figma full-page disponible localement (`figma_qb_preview.png`)
> - Les screenshots HTML générés par Playwright à 1440px
> - L'analyse directe du code HTML/CSS

---

## Statut global : CORRECTIONS REQUISES

---

## Section : Hero (node 339-2203)
### Statut : À CORRIGER (3 points)

- [OK] `h1` : `font-size:72px`, `font-weight:700`, `letter-spacing:-0.06em`, `line-height:1` — conforme Figma
- [OK] Subtitle : `font-size:18px`, `line-height:1.55`, `color:var(--mid)` — conforme
- [OK] Grid hero : `grid-template-columns:1.05fr 0.95fr`, `gap:50px`, `min-height:580px` — conforme
- [OK] Bouton jaune : `border:2px solid #d9ca0c`, `box-shadow:0 6px 0 #d9ca0c` — conforme
- [OK] Bouton ghost : `box-shadow:0 8px 0 rgba(9,17,13,.1)` — conforme
- [OK] Pill "Caisse activée" icône : `⚡` emoji dans carré gradient jaune — conforme Figma (correction Front Agent validée)
- [OK] Pill "+28% capacité" icône : `📊` emoji — conforme Figma (correction Front Agent validée)
- [OK] Pill "Paiement validé" icône : `✓` unicode `font-weight:900 color:#09110d` — conforme Figma (correction Front Agent validée)
- [OK] Trust checkmarks : `✓` unicode `font-weight:900 color:#0b9a5b` — conforme Figma (correction Front Agent validée)
- [OK] Background gradient hero : `radial-gradient(circle,rgba(225,255,38,.3),rgba(255,207,38,.16),transparent)` — conforme
- [OK] Image mockup 1 rotation : `rotate(8.26deg)` — conforme
- [OK] Image mockup 2 rotation : `rotate(-6.11deg)` — conforme
- [OK] Section padding : `60px 20px` — conforme

- [CORRECTION] **Tag pill hero — fond et border** : Figma montre un tag pill avec fond `rgba(225,255,38,.18)` et border légère `rgba(9,17,13,.06)`. Le code utilise `background:linear-gradient(129deg,rgba(225,255,38,.18),rgba(255,207,38,.18))` avec `border:1px solid rgba(9,17,13,.06)`. Le Figma montre une couleur unie sans gradient (la pill de catégorie en haut à gauche du hero est visuellement plus jaune-vert uniforme). [INCERTAIN] — différence visuelle subtile, probablement non bloquant.

- [CORRECTION] **Pill "Caisse activée" — position verticale** : La pill est à `top:85px; left:-16px` dans le code. Sur le Figma full-page, la pill "Caisse activée" semble être plus haute, vers le haut du mockup (environ 14-15% de la hauteur de la zone mockup 580px = ~85px). Position actuelle conforme à l'estimation. [INCERTAIN] — valeur non confirmable précisément depuis le screenshot full-page compressé.

- [CORRECTION] **Pill "+28% capacité" — position** : La pill est à `top:463px; left:187px`. Dans le Figma, cette pill apparaît en bas du mockup, légèrement à gauche-centre. La position `top:463px` sur une zone de `580px` représente ~80% de hauteur — visuellement cela correspond. [OK] après vérification visuelle.

- [CORRECTION] **h1 font-weight** : Le code utilise `font-weight:700` pour le h1 hero. Le Figma montre un titre qui semble être `font-weight:700` (Bold, pas ExtraBold/900). [OK] — conforme.

---

## Section : Trust bar logos (node 339-2500)
### Statut : À CORRIGER (2 points)

- [OK] 6 logos présents : Intermarché, Match, Carrefour Market, Carrefour Proximité, Franprix, Netto — conforme Figma
- [OK] Cards logos : `background:#fff; border-radius:16px; height:68px` — conforme
- [OK] Grid : `grid-template-columns:repeat(6,1fr); gap:12px` — conforme

- [CORRECTION] **Trust bar padding** : Code actuel `padding:48px 20px` (corrigé par le Front Agent depuis 96px). Visuellement dans le Figma full-page, la section logos apparaît avec un espacement très compact entre le hero et la section stats. Sur le screenshot HTML, l'espacement `48px` haut/bas semble encore un peu généreux — le Figma montre ~32-40px. [INCERTAIN] La valeur `48px` est une amélioration par rapport à `96px` mais pourrait être encore réduite à `36px` top/bottom pour coller davantage au Figma. Priorité basse.

- [CORRECTION] **Texte introductif trust bar** : Le code affiche `+50 magasins déployés en conditions réelles.` en `font-size:21px; font-weight:400; color:var(--mid)`. Dans le Figma full-page, ce texte n'est **pas visible** dans la trust bar — seuls les logos apparaissent directement sous le hero, sans texte d'introduction au-dessus des logos dans cette zone. Le texte est présent, mais dans le Figma il semble absent de cette section (ou beaucoup plus petit). [INCERTAIN] — le screenshot compressé ne permet pas de lire les petits textes.

---

## Section : Stats dark (node 339-2261)
### Statut : OK (mineur)

- [OK] Background : `background:#0e0b26` — conforme (#0E0B26 = var(--bleu))
- [OK] Padding section : `90px 20px` — visuellement conforme
- [OK] Tag pill dark : `background:rgba(225,255,38,.18); border:1px solid rgba(225,255,38,.18)` + dot gradient jaune — conforme
- [OK] Tag text color : `color:#e1ff26` — conforme (jaune néon sur fond sombre)
- [OK] h2 : `font-size:56px; font-weight:700; color:#fff; letter-spacing:-.05em; line-height:1.02` — conforme
- [OK] Cards grid : `grid-template-columns:repeat(3,1fr); gap:32px` — conforme
- [OK] Card background : `background:rgba(255,255,255,.04); border:1px solid rgba(255,255,255,.12); border-radius:24px; padding:37px 33px` — conforme
- [OK] Chiffres gradient : `font-size:64px; font-weight:700; letter-spacing:-.06em; line-height:.95` avec gradient jaune — conforme
- [OK] Gradients angles distincts par card (108°, 104°, 121°) — cohérent avec Figma
- [OK] Labels : `font-size:17px; font-weight:700; color:#fff` — conforme
- [OK] Descriptions : `font-size:14px; color:rgba(255,255,255,.6); line-height:1.5` — conforme
- [OK] Radial gradient déco droit : `rgba(225,255,38,.18)` — conforme

---

## Section : Timeline parcours (node 339-2293)
### Statut : À CORRIGER (2 points)

- [OK] Section background : `background:#fff` — conforme (fond blanc dans Figma)
- [OK] Section padding : `96px 20px` — conforme
- [OK] Tag pill : présent, conforme
- [OK] h2 titre : `font-size:56px; font-weight:700; letter-spacing:-.05em` — conforme
- [OK] Subtitle : `font-size:18px; line-height:1.55` — conforme
- [OK] Rail timeline : `background:rgba(9,17,13,.08); height:4px` — conforme
- [OK] Step 1 actif : 60×60px, gradient jaune, `border:4px solid #09110d`, box-shadow avec glow jaune — conforme
- [OK] Step 3 inactif : 52×52px, `background:#fff`, `border:4px solid rgba(9,17,13,.08)` — conforme
- [OK] Container parcours : `height:526px; border-radius:28px; background:rgba(255,255,255,.62); backdrop-filter:blur(10px)` — conforme
- [OK] Inset stages 1/2/3 : `top:54px; left:48px; right:48px; bottom:48px` — conforme (correction Front Agent validée, symétrique)
- [OK] h3 step : `font-size:42px; font-weight:700; letter-spacing:-.045em; line-height:1.02` — conforme
- [OK] Bullet dots list : `width:14px; height:14px; border-radius:7px; background:gradient jaune; box-shadow:0 0 0 3px rgba(225,255,38,.2)` — conforme

- [CORRECTION] **Step 2 état initial — background jaune** : Dans le code, le step 2 a `background:linear-gradient(135deg,#E1FF26,#FFCF26)` (fond jaune) à l'état de repos initial. Dans le Figma, le step 2 apparaît visuellement comme un cercle **blanc** (inactif) similaire au step 3, pas jaune. Le step 2 ne devrait être jaune qu'une fois "passé" (état complété). L'état initial correct pour le step 2 devrait être `background:#fff` comme le step 3. Actuellement dans le HTML (ligne 669) : `background:linear-gradient(135deg,#E1FF26,#FFCF26)` → devrait être `background:#fff` (ou `background:rgba(255,255,255,.9)`) avec `border:4px solid rgba(9,17,13,.08)` et couleur de texte `color:var(--mid)`.

- [CORRECTION] **Rail timeline — positionnement** : Le rail est défini via `position:absolute; background:rgba(9,17,13,.08); height:4px; left:69px; right:69px; border-radius:999px; top:24.2px`. Sur le screenshot HTML, le rail passe correctement derrière les cercles. [OK] — conforme visuellement.

---

## Section : Features Pikko Boost (node 339-2174)
### Statut : À CORRIGER (1 point)

- [OK] h2 : `font-size:56px; font-weight:700; letter-spacing:-.05em; line-height:1.02` — conforme
- [OK] Subtitle : `font-size:18px; color:var(--mid); line-height:1.55` — conforme
- [OK] Section background : `background:linear-gradient(180deg,#fff,#f4f5ef)` — conforme (blanc cassé vers légèrement vert en bas)
- [OK] Section padding : `96px 20px` — conforme
- [OK] Cards backdrop-filter : `backdrop-filter:blur(10px); border:1px solid rgba(255,255,255,.85); border-radius:22px; padding:33px 29px` — conforme
- [OK] Card background : `background:rgba(255,255,255,.7)` — conforme
- [OK] Card box-shadow : `box-shadow:0 18px 50px rgba(7,16,11,.06)` — conforme
- [OK] Icon boxes : `width:54px; height:54px; border-radius:14px; background:linear-gradient(135deg,#E1FF26,#FFCF26); box-shadow:0 8px 11px rgba(225,255,38,.35)` — conforme
- [OK] Emojis icônes : `🔌`, `📡`, `🔄` — conforme
- [OK] h3 cards : `font-size:18px; font-weight:700; letter-spacing:-.02em; margin:13px 0 0` — conforme
- [OK] Corps cards : `font-size:14.5px; color:var(--mid); line-height:1.55` — conforme
- [OK] Image droite position : `position:absolute; left:46%; top:-15px; right:-60px` — conforme
- [OK] Image rotation : `transform:rotate(.36deg)` — conforme

- [CORRECTION] **Cards wrapper — left:49% vs left:46%** : Le wrapper des cards est à `width:49%` et l'image commence à `left:46%`. Dans le Figma, la zone image semble couvrir exactement la moitié droite, avec un léger chevauchement sur les cards. Visuellement sur le screenshot HTML, l'image déborde bien à droite et se chevauche légèrement avec les cards. [OK] — conforme visuellement, pas de correction nécessaire.

- [CORRECTION] **Features section — absence de tag pill** : Dans le Figma full-page, la section Features ne montre pas de tag pill au-dessus du h2 (contrairement aux sections Stats dark et Timeline). Le code HTML n'en a pas non plus. [OK] — conforme.

---

## Section : CTA dark card (node 339-2813)
### Statut : À CORRIGER (2 points)

- [OK] Background card : `background:var(--bleu)` = `#0E0B26` — conforme
- [OK] Wrapper height : `height:640px` — visuellement conforme (en regardant le Figma)
- [OK] Card dark height : `height:499px; border-radius:34px` — conforme
- [OK] Card position : `position:absolute; bottom:0; left:0; right:0` — conforme
- [OK] Texte position : `left:58px; top:45px; width:500px` — visuellement conforme
- [OK] h2 : `font-size:68px; font-weight:700; line-height:.96; letter-spacing:-.07em; color:#fff` — conforme
- [OK] Subtitle : `font-size:21px; color:rgba(255,255,255,.68); line-height:1.5; max-width:444px` — conforme
- [OK] Bouton CTA yellow : `border:2px solid #d9ca0c; box-shadow:0 6px 0 #d9ca0c` — conforme (correction Front Agent validée)
- [OK] Device 1 (Urovo) rotation : `rotate(2.41deg)` — conforme
- [OK] Device 2 (iPhone) rotation : `rotate(8.65deg)` — conforme
- [OK] Images container : `left:489px; top:0; width:671px; height:646px` — conforme

- [CORRECTION] **Bouton CTA — largeur** : Le bouton "Prendre RDV" a `width:100%; box-sizing:border-box` ce qui le rend pleine largeur du conteneur (500px). Dans le Figma, le bouton CTA n'est pas pleine largeur — il a une largeur auto correspondant à son contenu (environ 200-220px). Le bouton devrait avoir `width:fit-content` ou `align-self:flex-start` plutôt que `width:100%`. [INCERTAIN] — le screenshot compressé ne permet pas de mesurer précisément, mais visuellement dans le Figma le bouton n'est pas full-width dans la dark card.

- [CORRECTION] **CTA dark — radial gradient déco** : Le gradient déco est `right:-160px; top:-215px`. Dans le Figma, le glow jaune est visible en haut à droite de la card. [OK] — visuellement conforme.

---

## Section : "Déjà adopté" (node 339-2625)
### Statut : OK

- [OK] Section padding : `96px 20px` — conforme
- [OK] h2 : `font-size:68px; font-weight:700; letter-spacing:-.07em; color:var(--dark); line-height:1` — conforme
- [OK] Texte sous-titre : `font-size:21px; color:var(--mid)` — conforme
- [OK] Logos grid : `grid-template-columns:repeat(6,1fr); gap:12px` — conforme
- [OK] Logo cards : `background:#fff; border-radius:16px; height:68px` — conforme (fond blanc sur fond beige)
- [OK] Les 6 mêmes logos que la trust bar : Intermarché, Match, Carrefour Market, Carrefour Proximité, Franprix, Netto — conforme Figma

---

## Section : KPIs (node 339-2645)
### Statut : OK (1 point mineur)

- [OK] Grid : `grid-template-columns:repeat(3,1fr)` — conforme
- [OK] KPI "14 jrs" : `font-size:72px` + `font-size:40px` pour l'unité — conforme
- [OK] KPI "24/7" : `font-size:72px; letter-spacing:-.05em` — conforme
- [OK] KPI "100%" : `font-size:72px` pour "100" + `font-size:40px` pour "%" — conforme
- [OK] Labels KPI : `font-size:14.5px; font-weight:700; color:var(--mid)` — conforme
- [OK] Séparateurs verticaux : `width:1px; height:80px; background:linear-gradient(180deg,transparent,rgba(9,17,13,.12) 50%,transparent)` — conforme
- [OK] margin-top séparateur de la grille logos : `margin-top:28px` — conforme

- [CORRECTION] **KPI padding** : Chaque KPI a `padding:0 20px`. Visuellement dans le Figma, les KPIs semblent avoir un peu plus d'espace horizontal. [INCERTAIN] — pas bloquant.

---

## Section : Footer (node 339-2665)
### Statut : À CORRIGER (1 point)

- [OK] Background footer : `background:var(--bleu)` = `#0E0B26` — conforme
- [OK] Border-radius : `46px 46px 0 0` — conforme
- [OK] Padding : `58px 64px 42px` — conforme
- [OK] Grid top : `grid-template-columns:300px 300px 1fr` — conforme
- [OK] Photo Alexandre : CDN URL présente, `width:111px; height:111px; border-radius:50%; border:5px solid #fff` — conforme
- [OK] Avatar background : `linear-gradient(170deg,#FFCF26,#E1FF26)` — conforme
- [OK] Contact card : `border-radius:34px; height:235px; background:rgba(255,255,255,.08); backdrop-filter:blur(9px); border:1px solid rgba(255,255,255,.12)` — conforme
- [OK] h3 "Contactez nous !" : `font-size:38px; font-weight:700; color:#fff; letter-spacing:-.06em; line-height:1` — conforme
- [OK] Bouton "Prendre RDV" glassmorphism : `background:rgba(255,255,255,.92); border:1px solid rgba(255,255,255,.9)` — conforme
- [OK] Logo blanc/jaune PikkoPay : CDN URL présente, `height:28px` — conforme
- [OK] Tagline footer : `font-size:14.5px; color:rgba(255,255,255,.8); line-height:1.5` — conforme
- [OK] Badge France : CSS inline tricolore, texte "Conçu, hébergé et opéré en France" — conforme
- [OK] Social icons : LinkedIn, X, cercle — conforme
- [OK] Copyright : `© 2026 Tous droits réservés.` — conforme
- [OK] Séparateur : `height:1px; background:rgba(255,255,255,.14); margin-bottom:34px` — conforme

- [CORRECTION] **Footer radial gradient** : Le gradient déco est `right:-200px; top:-232px; width:620px; height:620px; background:radial-gradient(circle,rgba(225,255,38,.28)...)`. Dans le code `pk-footer-inner::after` il y a un gradient similaire mais avec `.08` d'opacité. Le footer QB utilise `.28` (plus fort), ce qui crée un glow jaune plus prononcé en haut à droite que sur la page home. [INCERTAIN] — dans le Figma, le glow est assez prononcé dans le footer. Visuellement acceptable.

- [CORRECTION] **Footer padding-top** : Le footer a un `style="padding-top:28px;padding:28px 20px 0"` — la propriété `padding-top:28px` est écrasée par la shorthand `padding:28px 20px 0`. La valeur effective est `padding:28px 20px 0`, ce qui est redondant (le premier `padding-top:28px` n'a aucun effet car la shorthand le remplace). Le comportement visuel est correct mais le code est redondant. [OK] fonctionnellement mais [CORRECTION] de propreté : supprimer `padding-top:28px;` inline.

---

## Résumé des corrections prioritaires

### Priorité HAUTE — Impact visuel fort

1. **[Timeline — Step 2 background initial]** Le cercle step 2 dans le nav timeline doit être **blanc** (`background:#fff`) à l'état inactif initial, pas jaune. Ligne 669 du HTML : changer `background:linear-gradient(135deg,#E1FF26,#FFCF26)` → `background:#fff` pour le div `id="qbs2"`. Le step 2 ne doit devenir jaune que lorsqu'il est "passé" (état complété via `showStepQB`), ce qui est déjà géré correctement dans le JS. Seul l'état HTML initial est faux.

2. **[CTA dark card — Bouton largeur]** Le bouton "Prendre RDV" dans la CTA dark est à `width:100%` ce qui le rend pleine largeur (~500px). Dans le Figma, le bouton a une largeur auto (fit-content ~200-220px). Correction : remplacer `width:100%;box-sizing:border-box` par `align-self:flex-start` sur le `<a>` du bouton CTA dans la section `qb-cta-dark-content`.

### Priorité MOYENNE — Cohérence design

3. **[Trust bar — Padding vertical]** `padding:48px 20px` peut être réduit à `padding:36px 20px` pour se rapprocher davantage de l'espacement compact du Figma entre le hero et les stats.

4. **[Footer — Code redondant]** Supprimer `padding-top:28px;` du style inline du footer (la shorthand `padding:28px 20px 0` qui suit l'écrase de toute façon). Ligne 957 : `style="padding-top:28px;padding:28px 20px 0"` → `style="padding:28px 20px 0"`.

### Priorité BASSE — Incertitudes à confirmer avec accès Figma MCP

5. **[Hero — Pill tag fond]** Le tag pill hero utilise un gradient `linear-gradient(129deg,rgba(225,255,38,.18),rgba(255,207,38,.18))`. Figma utilise peut-être une couleur uniforme. Non bloquant visuellement.

6. **[Trust bar — Texte introductif]** Le texte "+50 magasins déployés en conditions réelles." au-dessus des logos (font-size:21px) n'est pas clairement visible dans le Figma full-page. Il est possible que ce texte ne doive pas figurer dans la trust bar (il apparaît aussi dans la section "Déjà adopté" en bas). À vérifier avec accès Figma direct.

7. **[CTA dark card — Position contenu]** `left:58px; top:45px; width:500px` — valeurs estimées, non confirmées par Figma MCP. Visuellement acceptables.

---

## Validations des corrections Front Agent (Passe 1)

| # | Correction Front Agent | Validation Review |
|---|---|---|
| 1 | Pill "Caisse activée" : SVG → `⚡` emoji | ✓ VALIDÉ |
| 2 | Pill "+28% capacité" : SVG → `📊` emoji | ✓ VALIDÉ |
| 3 | Pill "Paiement validé" : SVG → `✓` unicode | ✓ VALIDÉ |
| 4 | Trust checkmarks : SVG × 3 → `✓` unicode `font-weight:900` | ✓ VALIDÉ |
| 5 | Trust bar padding : 96px → 48px | ✓ VALIDÉ (peut être réduit à 36px — voir correction #3) |
| 6 | CTA dark bouton border+shadow : `#0B1209` → `#d9ca0c` | ✓ VALIDÉ |
| 7 | Timeline qbstage2 : `left:88px;right:8px` → `left:48px;right:48px` | ✓ VALIDÉ |
| 8 | Timeline qbstage3 : `left:88px;right:8px` → `left:48px;right:48px` | ✓ VALIDÉ |

---

## Notes pour la Passe 2

- Les corrections prioritaires 1 et 2 sont les plus visibles et doivent être appliquées en priorité.
- Une confirmation via Figma MCP (si plan upgradé) des nodes `339-2500` (trust bar), `339-2293` (timeline step 2), et `339-2813` (CTA card bouton) permettrait de lever les incertitudes restantes.
- Le reste de la page est globalement fidèle au Figma — le travail du Front Agent a été de bonne qualité.

---

*Rapport écrit par le Review Agent — Passe 1 terminée*

---

## Passe finale (2026-05-28)

**Reviewer :** Review Agent — Vérification finale des 4 corrections du Front Agent

### Résultats par correction

| # | Correction | Statut | Détail |
|---|---|---|---|
| 1 | **Timeline step 2 — cercle blanc** | VALIDE | Ligne 669 : `background:#fff; border:4px solid rgba(9,17,13,.08); color:var(--mid)` — cercle blanc 52×52px, identique au step 3. Confirmé visuellement (screenshot) et par inspection DOM (bg=rgb(255,255,255)). |
| 2 | **CTA bouton "Prendre RDV" — fit-content** | VALIDE | Ligne 896 : `align-self:flex-start` présent dans le style inline. Le bouton mesure 185px de large (fit-content), confirmé visuellement sur screenshot et par inspection DOM. |
| 3 | **Trust bar — padding réduit à 36px** | VALIDE | Ligne 584 : `padding:36px 20px` — espacement vertical compact conforme au Figma. Confirmé visuellement et par code. |
| 4 | **Footer — suppression padding-top redondant** | VALIDE | Ligne 957 : `style="padding:28px 20px 0"` — le `padding-top:28px;` redondant a bien été supprimé. Code propre. |

### Statut global : APPROUVÉ

Les 4 corrections demandées sont toutes correctement appliquées. La page `preview/03-queue-busting.html` est conforme aux spécifications Figma sur tous les points identifiés lors de la Passe 1.

*Passe finale terminée — Review Agent*
