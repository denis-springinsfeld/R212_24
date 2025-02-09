# Animations CSS

Il existe deux moyens de créer des animations en CSS : les **transitions**, et les **keyframes**.

## 1 - Transition

Les **transitions CSS** permetent de définir la transition entre deux états d'un élément,
elles permettent ainsi de contrôler la vitesse d'animation lorsque une ou des propriétés CSS sont modifiées.
Si on souhaite passer un élément de blanc à noir, on pourra utiliser les transitions CSS afin que cette modification soit effectuée progressivement, selon une courbe d'accélération donnée.

Afin de gérer cette transition, cinq propriétés sont définies :

- `transition-property` : la (les) propriété(s) à animer (propriétés séparées par une ',' ) || all;

- `transition-duration` : la durée de la transition ;

- `transition-delay` : le délai avant que l’animation ne se lance (valeur négative possible);

- `transition-timing-function` : la méthode d’interpolation (départ rapide, lent…) ;
  - `ease` : rapide au début et ralenti à la fin.
  - `linear` : vitesse constante.
  - `ease-in` : lent au début et accélère de plus en plus à la fin.
  - `ease-out` : rapide au début et de plus en plus lent à la fin.
  - `ease-in-out` : départ et fin lents.
  - `cubic-bezier()` : permet de personnalisser finement la transition (cubic-bezier.com).

`transition` : c’est la propriété raccourcie des quatre précédentes.

### / Modifiez les éléments voisins avec les pseudo-classes et sélecteurs avancés

L’utilisation d’une `pseudo-classe` pour déclencher une transition est l’un des points essentiels des animations CSS.

Une `pseudo-classe` s’apparente à un if/else pour le CSS. Elle est interprétée par le navigateur, qui applique le style si la condition de la `pseudo-classe` est à `true`. Pour notre bouton, si la condition du survol de souris est vérifiée, le style défini dans la `pseudo-classe :hover` est appliqué.

`:hover` déclenché au survol de la souris ;

`:active` activé au clic de l'utilisateur (le plus souvent pour les liens et boutons) ;

`:focus` se déclenche lorsque son élément reçoit le focus (soit il est sélectionné à l'aide du clavier, soit il est activé avec la souris);

`:valid` lorsque la validation du contenu s'effectue correctement par rapport au type de donnée attendu;

`:invalid` inversement, correspond à un élément dont la validation du contenu ne s'effectue pas correctement par rapport au type de donnée attendu;

`:is()` elle prend un sélecteur en argument et permet de cibler les éléments qui sont représentés par cet/ces argument/s;

`:not()` négation. Elle prend un sélecteur en argument et permet de cibler les éléments qui ne sont pas représentés par cet argument ;

`:has()` elle prend un sélecteur en argument et permet de cibler les éléments qui ont un ou plusieurs descendants qui correspondent à cet argument ;

`:nth-child()` elle prend un argument en paramètre et permet de cibler les éléments qui correspondent à cet argument ;

`:nth-of-type()` elle prend un argument en paramètre et permet de cibler les éléments qui correspondent à cet argument ;

`:first-child` correspond au premier enfant d’un élément ;

`:last-child` correspond au dernier enfant d’un élément ;

`:only-child` correspond à un élément qui est le seul enfant de son parent ;

`:checked` correspond aux input de type checkbox, option ou radio qui sont cochés ;

`:enabled` correspond à un élément avec lequel on peut interagir ;

`:disabled` correspond à un élément dont l'interaction a été bloquée.
...

Pour qu’une pseudo-classe déclenche une transition sur un autre élément, cet élément doit être le voisin suivant direct (ou sibling en anglais) dans le document HTML. De fait, nous devons utiliser le `combinateur` d’adjacence **+** pour créer la transition sur l’élément voisin.

Maintenant, utilisons la pseudo-classe **`:focus`**.
Elle nous permet de donner un feedback immédiat à l’utilisateur lorsqu’il sélectionne l’input en surlignant le bord de l’input.

```html
<div class="container">
  <div class="form">
    <div class="form__group">
      <label for="">email</label>
      <input type="email" name="" id="" />
    </div>
  </div>
</div>
```

```css
.form__input {
  border: 2px solid rgb(153, 153, 153);
  border-radius: 100px;
  color: rgb(104, 104, 104);
  font-size: 2.5rem;
  outline: none;
  padding: 0.5em 1.5em;
  margin-top: 1em;
  width: 100%;
  transition: background-color 500ms;
}

.form__input:focus {
  border: 2px solid rgb(57, 57, 57);
  color: rgb(57, 57, 57);
}

.form__input:not(:focus):invalid {
  background-color: #ff0000;
  border: 2px solid #ff0000;
  color: #a82929;
}
```

`:not()` passe à true lorsque le sélecteur qu’elle contient est à `false`.

Dans notre cas, le style est appliqué si l’input n’est pas en état `:focus` et si `:invalid` est à true. Ce qui nous permet d’obtenir l’effet recherché : la couleur rouge d’avertissement pour e-mail invalide n’apparaît qu’une fois que l’utilisateur a terminé de taper son adresse e-mail.

---

```css
    .btn {
        ...
        color: #fff;
        background: var(--clr-primary);
        cursor: pointer;
        padding: 1em 3em;
        border-radius: 10rem;
    }

    .ball {
        width: calc(var(--ball-size) * 1rem);
        height: calc(var(--ball-size) * 1rem);
        background: var(--clr-secondary);
        margin-bottom: 1em;
        border-radius: 50%;
        transform: scale(0.1);
        transition: transform .4s;
    }

    .btn:active + .ball{
        transform: scale(1.0);
    }
```

Les `pseudo-classes` sont essentielles pour déclencher une transition en CSS. Une transition peut également être déclenchée par un changement de classe en JavaScript

### /Combiner transitions

```html
<body>
  <div class="container">
    <div class="btn">Survole-moi!</div>
  </div>
</body>
```

```css
.btn {
  background-color: blue;
  border-radius: 10rem;
  cursor: pointer;
  font-size: 3rem;
  overflow: hidden;
  padding: 1.85em 3em;
  transition: transform 0.4s, background-color 0.3s 0.4s;
}

.btn:hover {
  transform: scale(1.13);
  background-color: green;
}
```

### /Les fonctions de timing

l’accélération et la décélération des transitions sont contrôlées par la propriété `transition-timing-function` qui prend en argument une fonction de timing. Les fonctions de timing les plus utilisées sont les fonctions de Bézier. Elles sont définies par 4 points de contrôle (x1, y1, x2, y2) qui définissent la forme de la courbe. Pour les définir, vous pouvez utiliser le site
cubic-bezier.com.

---

## 2. Animation

### /Animation CSS

Une animation CSS correspond à plusieurs transitions qui s’enchaînent.
Pour cela, chaque transition est donc définie sous forme d’étape (en pourcentage de l’animation globale) via la règle `@keyframes`. Puis l'appliquer sur l'élément que vous voulez animer.

```css
@keyframes nomAnim {
  0% {
    scale: .1;
  }
  50% {
    scale: 1.5;
  }
  100% {
    scale: 1;
  }
}

@keyframes nomAnim {
  from,
  to {
    scale: 1.5;
  }
```

`animation-name` : le nom de l’animation à utiliser ;

`animation-duration` : la durée complète de l’animation ;

`animation-delay` : le délai avant que l’animation ne se lance ;

`animation-timing-function` : la méthode d’interpolation (départ rapide, lent…) entre chaque étape;

`animation-iteration-count` : le nombre de fois où l’animation est répétée. Le mot-clé `infinite` permet d’effectuer l’animation en boucle;

`animation-direction` normal | reverse | alternate | alternate-reverse : permet de jouer l’animation en sens inverse;

`animation-fill-mode` forward | backward | both : état des éléments avant et après l’exécution de l’animation;

`animation-play-state` running | paused : permet de mettre l’animation en pause ;

`animation` : c’est la propriété raccourcie des huit précédentes.

> **NEW** > `animation-timeline: scroll()` : associe l'animation à la position de défilement de la page.
