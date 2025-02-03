# TP1/

> ! Pour chaque exercice utiliser le découpage du CSS vu en SAé et en TD :

- base.css
- reset.css
- variables.css
- components.css
- utilities.css

⚠️ Vous adopterez une approche **mobile first**.

## EXERCICE 1

### DS

#### Primitive Tokens

```css
--clr-primary-400: hsl(263 55% 52%);
--clr-primary-800: hsl(262, 32%, 64%);
--clr-secondary-alpha: hsla(217, 19%, 35%, 0.25);
--clr-secondary-400: hsl(217 19% 35%);
--clr-secondary-500: hsl(219 29% 14%);
--clr-neutral-100: hsl(0 0% 100%);
--clr-neutral-200: hsl(210 46% 95%);
--clr-neutral-300: hsl(0 0% 81%);

--ff-primary: "Barlow Semi Condensed", sans-serif;

--fw-500: 500;
--fw-600: 600;

--fs-300: 0.85rem;
--fs-400: 0.95rem;
--fs-500: 1.5rem;
```

#### Semantic Tokens

```css
--_clr-forground: var(--clr-secondary-500);
--_clr-background: var(--clr-neutral-100);
```

#### Break-points

Break-points : 33rem | 54rem | 75rem

### ETAPE 1

- Création d'une card :
  BLOCK : Création d'une card avec ses différents ELEMENTS.
  cf: Sreen/card.png

- Création de variants de card :
  MODIFIER : Création de différents MODIFIERS permettant de changer les couleurs de la card et/ou ajouter un élément décoratif en arrière plan.
  cf: Screen/card--purple.png

### ETAPE 2

Création d'un container grid.
⚠️ Utilisez deux méthodes de définition de la grille.

cf: Screen/S.png, M.png...

---

## EXERCICE 2

### DS

Typo Family: DM Sans
Weights: 400, 500

// Primitive Tokens

hsl(254, 88%, 90%)
hsl(256, 67%, 59%)

hsl(31, 66%, 93%)
hsl(39, 100%, 71%)

hsl(0, 0%, 100%)
hsl(0, 0%, 7%)

// Semantic Tokens
à définir

### ETAPE 1

BLOCK : Création d'une card

### ETAPE 2

Création d'un container grid.

cf. Xs.jpg & XL.jpg

---

## EXERCICE 3

### DS

Typo Family:
Heebo
Bungee
Bungee Shade

// Primitive Tokens

rgb(2, 2, 177);
rgba(2, 2, 177, 0.9);
rgb(255, 255, 255);

// Semantic Tokens
à définir

### ETAPE 1

BLOCK : Création d'une card

cf. card3.png

### ETAPE 2

Création d'un container grid.

cf. exo3.mov
