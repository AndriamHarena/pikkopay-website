# QueueBusting Design Log — Passe 1

**Date :** 2026-05-27
**Agent :** Front Agent
**Fichiers modifiés :**
- `C:\Users\Emma\Desktop\Harena\pikkopay-website\03-queue-busting.html` (fragment)
- `C:\Users\Emma\Desktop\Harena\pikkopay-website\preview\03-queue-busting.html` (preview complet)

---

## Contexte

Figma MCP a été limité à 1 appel (plan Starter) — seule la section HERO SPLIT (node `339-2203`) a pu être récupérée en code complet + screenshot. Pour les autres sections, l'analyse s'est appuyée sur :
- Le screenshot Figma full-page disponible localement (`figma_qb_preview.png`)
- La comparaison visuelle section par section avec le code HTML existant

---

## Section HERO SPLIT (node 339-2203) — Figma vs HTML

### Floating pills — icônes

**Constaté dans Figma :**
- Pill "Caisse activée" : icône `⚡` (emoji, `font-size:14px`, centré dans carré 28×28 gradient jaune)
- Pill "+28% capacité" : icône `📊` (emoji, `font-size:14px`)
- Pill "Paiement validé" : icône `✓` (unicode, `font-weight:900`, `color:#09110d`)

**Constaté dans HTML existant :**
- Pill "Caisse activée" : SVG `<polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/>` (éclair SVG générique)
- Pill "+28% capacité" : SVG barres verticales (bar chart SVG générique)
- Pill "Paiement validé" : SVG polyline checkmark

**Modification appliquée :** SVG remplacés par emojis/unicode dans les 3 pills (fragment + preview)

---

### Trust checkmarks (section inférieure du hero)

**Constaté dans Figma :**
- Les 3 items "Activation en 14 jours / Sans matériel / Compatible Android" utilisent `✓` unicode text dans un span `font-weight:900 color:#0b9a5b`

**Constaté dans HTML existant :**
- SVG checkmarks (polyline)

**Modification appliquée :** SVG remplacés par `<span style="font-size:13.5px;font-weight:900;color:#0b9a5b;line-height:1">✓</span>` (fragment + preview)

---

### Autres propriétés Hero vérifiées (conformes, pas de modification)

| Propriété | Figma | HTML | Statut |
|---|---|---|---|
| h1 font-size | 72px | 72px | ✓ conforme |
| h1 letter-spacing | -4.32px (= -0.06em à 72px) | -0.06em | ✓ conforme |
| h1 line-height | 72px (= 1) | 1 | ✓ conforme |
| h1 font-weight | 700 | 700 | ✓ conforme |
| Subtitle font-size | 18px | 18px | ✓ conforme |
| Subtitle line-height | ~1.55 | 1.55 | ✓ conforme |
| Grid hero columns | 1.05fr / 0.95fr | 1.05fr / 0.95fr | ✓ conforme |
| Grid gap | 50px | 50px | ✓ conforme |
| Btn yellow border | #d9ca0c | #d9ca0c | ✓ conforme |
| Btn yellow shadow | 0 6px 0 #d9ca0c | 0 6px 0 #d9ca0c | ✓ conforme |
| Btn ghost shadow | 0 8px 0 rgba(9,17,13,.1) | 0 8px 0 rgba(9,17,13,.1) | ✓ conforme |
| Mockup img1 rotation | 8.26deg | 8.26deg | ✓ conforme |
| Mockup img2 rotation | -6.11deg | -6.11deg | ✓ conforme |
| Pill "Caisse activée" top | ~14.66% de 580px = ~85px | top:85px | ✓ conforme |
| Section padding | 60px top | 60px | ✓ conforme |
| Background gradient | rgba(225,255,38,.3) | rgba(225,255,38,.3) | ✓ conforme |

---

## Section TRUST BAR logos (node 339-2500)

**Figma MCP non disponible** — analyse visuelle screenshot.

**Constaté :** Dans le screenshot Figma, la section logos entre le hero et les stats a un espacement vertical très inférieur à 96px. Elle semble coller plus près du hero et de la stats dark.

**Modification appliquée :** `padding:96px 20px` → `padding:48px 20px` (fragment + preview)

**Incertitude :** La valeur exacte n'a pas été confirmée par Figma MCP. Le Review Agent devrait vérifier. La valeur `48px` vient d'une estimation visuelle du screenshot.

---

## Section STATS DARK (node 339-2261)

**Figma MCP non disponible** — analyse code vs screenshot.

**Propriétés vérifiées visuellement :**
- Fond `#0e0b26` : ✓ conforme (`background:#0e0b26`)
- Padding `90px 20px` : semble légèrement tight mais acceptable
- Tag pill : `background:rgba(225,255,38,.18);border:1px solid rgba(225,255,38,.18)` + dot gradient jaune ✓
- Titre h2 : `font-size:56px;font-weight:700;color:#fff;letter-spacing:-.05em` ✓
- Grille 3 colonnes cards : `background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.12);border-radius:24px` ✓
- Chiffres gradients : angles différents par card (108°, 104°, 121°) — non confirmé par Figma MCP mais visuellement cohérent
- Font-size chiffres : `64px;font-weight:700;letter-spacing:-.06em` ✓

**Aucune modification** — semble conforme

---

## Section TIMELINE PARCOURS (node 339-2293)

**Figma MCP non disponible** — analyse code.

**Corrections appliquées :**
- `qbstage2` et `qbstage3` avaient `left:88px;right:8px` alors que `qbstage1` a `left:48px;right:48px`. Cette asymétrie était incorrecte.
- **Correction :** `left:88px;right:8px` → `left:48px;right:48px` pour les étapes 2 et 3 (fragment + preview)

**Propriétés vérifiées :**
- Rail fond : `background:rgba(9,17,13,.08);height:4px` ✓
- Cercle actif (étape 1) : 60×60px, gradient jaune, border `4px solid #09110d`, shadow ring `rgba(225,255,38,.25)` ✓
- Cercle inactif (étapes 2/3) : 52×52px ✓
- Conteneur parcours : `height:526px;border-radius:28px;background:rgba(255,255,255,.62)` ✓
- h3 steps : `font-size:42px;letter-spacing:-.045em` ✓

**Incertitude :** Le style exact du step 2 (jaune vs blanc à l'état initial) n'est pas confirmé par Figma. Le step 2 a un fond jaune mais couleur de texte `var(--mid)` — cela semble être un état "next" intentionnel mais à vérifier.

---

## Section FEATURES Pikko Boost (node 339-2174)

**Figma MCP non disponible** — analyse code + screenshot.

**Propriétés vérifiées :**
- Emojis dans icônes jaunes : `🔌`, `📡`, `🔄` ✓ (déjà corrects)
- Icône box : `width:54px;height:54px;border-radius:14px;background:linear-gradient(135deg,#E1FF26,#FFCF26)` ✓
- Cards : `border-radius:22px;padding:33px 29px;backdrop-filter:blur(10px)` ✓
- Image droite : `transform:rotate(.36deg)` ✓

**Aucune modification** — semble conforme

---

## Section CTA DARK (node 339-2813)

**Figma MCP non disponible** — analyse code + design system.

**Correction appliquée :**
- Bouton CTA "Prendre RDV" avait `border:2px solid #0B1209` (quasi-noir) + `box-shadow:0 6px 0 #0B1209` — incohérent avec le design system PikkoPay où le bouton jaune doit avoir `border:#d9ca0c` + `box-shadow:0 6px 0 #d9ca0c`
- **Correction :** `#0B1209` → `#d9ca0c` (fragment + preview)

**Propriétés vérifiées (conformes) :**
- Fond CTA : `var(--bleu)` = `#0E0B26` ✓
- h2 : `font-size:68px;letter-spacing:-.07em;line-height:.96` ✓
- Desc : `font-size:21px;color:rgba(255,255,255,.68)` ✓
- Card border-radius : `34px` ✓
- Device 1 (iPhone) rotation : `8.65deg` ✓
- Device 2 (Urovo) rotation : `2.41deg` ✓

**Incertitude :**
- Le CTA dark a `left:58px;top:45px;width:500px` pour le contenu texte — position absolue, non vérifiée par Figma MCP
- La hauteur exacte de la dark card (`499px`) et du wrapper (`640px`) non vérifiée

---

## Section "Déjà adopté" + KPIs (nodes 339-2625, 339-2645)

**Figma MCP non disponible** — analyse code + screenshot.

**Propriétés vérifiées (conformes) :**
- h2 : `font-size:68px;font-weight:700;letter-spacing:-.07em` ✓
- Logos grid : 6 colonnes, cards blanches `border-radius:16px;height:68px` ✓
- KPIs : `font-size:72px;font-weight:700;letter-spacing:-.05em` pour les grands nombres ✓
- Séparateurs : `1px gradient rgba(9,17,13,.12)` ✓

**Aucune modification** — semble conforme

---

## Footer (node 339-2665)

**Figma MCP non disponible** — analyse code + screenshot.

**Propriétés vérifiées (conformes) :**
- Fond footer : `var(--bleu)` = `#0E0B26` ✓
- Border-radius : `46px 46px 0 0` ✓
- Photo Alexandre : CDN URL présente ✓
- Logo blanc/jaune PikkoPay : CDN URL présente ✓
- Grid top : `300px 300px 1fr` ✓
- Carte contact : `border-radius:34px;height:235px;background:rgba(255,255,255,.08)` ✓
- Bouton "Prendre RDV" : glassmorphism `background:rgba(255,255,255,.92)` ✓
- Flag FR : CSS inline tricolore ✓

**Aucune modification** — semble conforme

---

## Résumé des modifications appliquées

| # | Section | Propriété | Avant | Après |
|---|---|---|---|---|
| 1 | Hero | Pill "Caisse activée" icône | SVG polygon (éclair) | `⚡` emoji |
| 2 | Hero | Pill "+28% capacité" icône | SVG barres | `📊` emoji |
| 3 | Hero | Pill "Paiement validé" icône | SVG polyline | `✓` unicode bold |
| 4 | Hero | Trust checkmarks | SVG polyline × 3 | `✓` unicode `font-weight:900 color:#0b9a5b` × 3 |
| 5 | Trust bar | Section padding | `96px 20px` | `48px 20px` |
| 6 | CTA Dark | Bouton border+shadow | `#0B1209` (quasi-noir) | `#d9ca0c` (jaune foncé) |
| 7 | Timeline | qbstage2 position | `left:88px;right:8px` | `left:48px;right:48px` |
| 8 | Timeline | qbstage3 position | `left:88px;right:8px` | `left:48px;right:48px` |

---

## Points à vérifier par le Review Agent (incertitudes)

1. **Trust bar padding** : `48px` estimé visuellement — confirmer valeur exacte avec Figma nodes `339-2500`
2. **Timeline étape 2 état initial** : fond jaune `linear-gradient(135deg,#E1FF26,#FFCF26)` vs fond blanc — à confirmer avec node `339-2293`
3. **CTA height exact** : dark card `499px`, wrapper `640px`, `left:489px` pour img container — à vérifier avec nodes `339-2813` et `339-2821`
4. **Stats dark padding** : `90px 20px` — à confirmer avec node `339-2261`
5. **Floating pill "Caisse activée" position** : `top:85px;left:-16px` — à confirmer précisément (Figma indique `inset:14.66% 74.17% 76.72% -2.99%` sur la zone mockup 580px haut)
6. **Step 2 timeline background color** — inactif devrait être blanc ou jaune ? (à confirmer)

---

*Rapport écrit par le Front Agent — Passe 1 terminée*

---

# QueueBusting Design Log — Passe 2

**Date :** 2026-05-28
**Agent :** Front Agent
**Fichiers modifiés :**
- `C:\Users\Emma\Desktop\Harena\pikkopay-website\03-queue-busting.html` (fragment)
- `C:\Users\Emma\Desktop\Harena\pikkopay-website\preview\03-queue-busting.html` (preview complet)

## Corrections appliquées (validées par le Review Agent)

| # | Priorité | Section | Propriété | Avant | Après |
|---|---|---|---|---|---|
| 1 | HAUTE | Timeline — Step 2 | `background` du cercle `#qbs2` | `linear-gradient(135deg,#E1FF26,#FFCF26)` (jaune) | `#fff` (blanc, état inactif comme le step 3) |
| 2 | HAUTE | CTA dark — Bouton "Prendre RDV" | `display`, `width`, suppression `box-sizing` | `display:flex;width:100%;box-sizing:border-box` | `display:inline-flex;align-self:flex-start` (fit-content) |
| 3 | MOYENNE | Trust bar (logos) | `padding` de la `<section>` | `padding:48px 20px` | `padding:36px 20px` |
| 4 | MOYENNE | Footer `<footer>` | Attribut `style` | `padding-top:28px;padding:28px 20px 0` (redondant) | `padding:28px 20px 0` (simplifié) |

## Notes

- La correction #1 (step 2 blanc) aligne l'état initial avec le comportement attendu : seul le step 1 est actif au chargement. Le step 2 adopte maintenant le même style visuel inactif que le step 3.
- La correction #2 (bouton fit-content) retire `width:100%` et `box-sizing:border-box` qui forçaient le bouton à prendre toute la largeur du conteneur de 500px. Le passage à `inline-flex` + `align-self:flex-start` lui permet de se dimensionner à son contenu (~200px).
- La correction #3 (trust bar padding 48→36px) affine l'espacement vertical de la section logos pour mieux correspondre au Figma.
- La correction #4 (footer) est purement un nettoyage CSS : `padding-top:28px` était écrasé par la propriété `padding` shorthand qui suivait immédiatement.

---

*Rapport écrit par le Front Agent — Passe 2 terminée*
