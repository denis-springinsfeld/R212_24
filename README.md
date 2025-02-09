# Aide-Mémoire sur les Transformations en CSS

Ce document présente un récapitulatif complet des différentes opérations de transformation en CSS, incluant la propriété classique **transform** ainsi que les nouvelles propriétés individuelles **translate**, **rotate**, **scale** et **skew** (niveau 2).

---

## 1. La Propriété `transform` (CSS Transforms Niveau 1)

La propriété `transform` permet d’appliquer une ou plusieurs fonctions de transformation à un élément. **L'ordre des transformations est important**, car chaque opération s'appuie sur le résultat de la précédente.

### Fonctions de Transformation Classiques

- **`translate(tx, ty)`**

  - **Description :** Déplace l’élément de `tx` (axe X) et `ty` (axe Y).
  - **Exemple :**
    ```css
    .element {
      transform: translate(50px, 100px);
    }
    ```

- **`translateX(tx)` / `translateY(ty)`**

  - **Description :** Déplace uniquement sur l’axe X ou Y.
  - **Exemple :**
    ```css
    .element {
      transform: translateX(50px);
      /* ou */
      transform: translateY(100px);
    }
    ```

- **`rotate(angle)`**

  - **Description :** Fait pivoter l’élément autour de son centre (sauf si vous modifiez l’origine de transformation).
  - **Exemple :**
    ```css
    .element {
      transform: rotate(45deg);
    }
    ```

- **`scale(sx, sy)`**

  - **Description :** Met à l’échelle l’élément selon les axes X et Y. Si `sy` est omis, la valeur est identique à `sx`.
  - **Exemple :**
    ```css
    .element {
      transform: scale(1.5); /* Agrandissement uniforme */
    }
    ```

- **`scaleX(sx)` / `scaleY(sy)`**

  - **Description :** Met à l’échelle uniquement sur un axe.
  - **Exemple :**
    ```css
    .element {
      transform: scaleX(2);
      /* ou */
      transform: scaleY(0.5);
    }
    ```

- **`skew(ax, ay)`**

  - **Description :** Incline l’élément selon les angles `ax` (axe X) et `ay` (axe Y).
  - **Exemple :**
    ```css
    .element {
      transform: skew(20deg, 10deg);
    }
    ```

- **`skewX(ax)` / `skewY(ay)`**
  - **Description :** Incline uniquement sur un axe.
  - **Exemple :**
    ```css
    .element {
      transform: skewX(20deg);
      /* ou */
      transform: skewY(10deg);
    }
    ```

### Combinaison de Transformations

Vous pouvez combiner plusieurs fonctions dans une seule déclaration :

```css
.element {
  transform: translate(50px, 100px) rotate(30deg) scale(1.5);
}
```

> **Note :** Attention à l’ordre des fonctions, qui peut influencer le résultat final.
> **Note :** Attention redéfinir une transformation annule les précédentes.

## 2. Les nouvelles propriétés de transformation (CSS Transforms niveau 2)

Afin de faciliter l’animation et la gestion individuelle des transformations, les nouvelles propriétés permettent de définir séparément chaque transformation. Elles offrent notamment l’avantage d’animer uniquement la transformation souhaitée sans redéfinir l’ensemble de la transformation appliquée.

### Propriétés individuelles

- **`translate`**

  - **Description :** Applique une **translation**.
  - **Exemple :**

  ```css
  .element {
    translate: 50px 100px; /* (tx, ty) */
  }
  ```

- **`rotate`**
  - **Description :** Applique une rotation.
  - **Exemple :**
    ```css
    .element {
      rotate: 30deg;
    }
    ```
- **`scale`**
  - **Description :** Applique une mise à l’échelle.
  - **Exemple :**
    ```css
    .element {
      scale: 1.5; /* Uniforme */
      /* Ou pour définir séparément X et Y : */
      /* scale: 1.5 2; */
    }
    ```
- **`skew`**
  - **Description :** Applique une inclinaison sur les axes X et Y.
  - **Exemple :**
    ```css
    .element {
      skew: 20deg 10deg;
    }
    ```

### Exemple d’utilisation combinée

Les nouvelles propriétés se cumulent selon un ordre prédéfini (généralement : translate → rotate → skew → scale).
Voici un exemple d’animation utilisant ces propriétés :

```css
.element {
  /* Définition initiale */
  translate: 0 0;
  rotate: 0deg;
  scale: 1;
  transition: translate 0.5s, rotate 0.5s, scale 0.5s;
}

.element:hover {
  /* Transformation lors du survol */
  translate: 100px 0;
  rotate: 360deg;
  scale: 1.2;
}
```

Remarque : Bien que ces nouvelles propriétés soient de plus en plus supportées par les navigateurs modernes, vérifiez toujours la compatibilité pour les projets nécessitant un support étendu.

## 3. Autres aspects importants

### Origine de transformation

Par défaut, l’origine de transformation est le centre de l’élément. Vous pouvez la modifier avec **`transform-origin`**.

```css
.element {
  transform-origin: top left; /* Autres valeurs possibles : center, 50% 50%, etc. */
}
```
