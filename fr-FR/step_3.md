### Différentes positions de repos de la tête

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

Pour le moment, le micro:bit enregistre un mouvement chaque fois que le micro:bit n'est **pas** à niveau.

Pour ce projet, le micro:bit est placé sous un oreiller, car il serait inconfortable de le porter sur la tête !

Lorsque tu t'allonges, le poids de ta tête sur ton oreiller fera probablement rouler le micro:bit de sorte qu'il ne sera pas complètement à niveau.

Ce sera la **position de repos**. 

Tu ne dois enregistrer un mouvement que si le micro:bit est déplacé de sa position de repos. 

</div>
</div>

### Vérifier le mouvement vers la GAUCHE à partir de la position de repos

Tu dois savoir s'il existe une différence entre la position de repos et la position de rotation actuelle.

--- task ---

Dans le menu `Maths`{:class='microbitmath'}, prends un bloc `0 - 0`{:class='microbitmath'}.

Place-le dans le bloc de comparaison `-10` du `<`{:class='microbitlogic'}.

--- /task ---

--- task ---

Ouvre le menu `Variables`{:class='microbitvariables'} et clique sur **Créer une variable**.

Nomme ta nouvelle variable `positionRepos`.

--- /task ---

--- task ---

Dans le menu `Variables`{:class='microbitvariables'}, prends le bloc `positionRepos`{:class='microbitvariables'}.

Place-le dans le premier bloc `0` à gauche du bloc `0 - 0`{:class='microbitmath'}.

--- /task ---

--- task ---

Remplace le `0` à droite du `-`{:class='microbitmath'} par `10`.

Ton code devrait ressembler à ceci :

```microbit
let mouvements = 0
basic.forever(function () {
    let positionRepos = 0
    if (input.rotation(Rotation.Roll) < positionRepos - 10 || input.rotation(Rotation.Roll) > 10) {
        mouvements += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        basic.clearScreen()
    }
})
```

--- /task ---

### Vérifier le mouvement vers la DROITE à partir de la position de repos

--- task ---

Dans le menu `Maths`{:class='microbitmath'}, prends un bloc `0 + 0`{:class='microbitmath'}.

Place-le dans le bloc de comparaison `10` du `>`{:class='microbitlogic'}.

--- /task ---

--- task ---

Dans le menu `Variables`{:class='microbitvariables'}, prends un autre bloc `positionRepos`{:class='microbitvariables'}.

Place-le dans le premier bloc `0` à gauche du bloc `0 + 0`{:class='microbitmath'}.

--- /task ---

--- task ---

Remplace le `0` à droite du `+`{:class='microbitmath'} par `10`.

Ton code devrait ressembler à ceci :

```microbit
let mouvements = 0
basic.forever(function () {
    let positionRepos = 0
    if (input.rotation(Rotation.Roll) < positionRepos - 10 || input.rotation(Rotation.Roll) > positionRepos + 10) {
        mouvements += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        basic.clearScreen()
    }
})
```

--- /task ---

### Définir une nouvelle position de repos après chaque mouvement

Chaque fois que le micro:bit est déplacé vers une nouvelle position de repos, tu dois définir la position actuelle comme nouvelle position de repos, afin de pouvoir l'utiliser dans ta comparaison.

--- task ---

Dans le menu `Variables`{:class='microbitvariables'}, prends le bloc `définir`{:class='microbitvariables'}.

Place-le sous le bloc `pause`{:class='microbitbasic'}.

--- /task ---

--- task ---

Duplique le bloc `rotation`{:class='microbitinput'} et place-le dans le `0` du bloc `définir`{:class='microbitvariables'}.

Ton code devrait ressembler à ceci :

```microbit
let positionRepos = 0
let mouvements = 0
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < positionRepos - 10 || input.rotation(Rotation.Roll) > positionRepos + 10) {
        mouvements += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        positionRepos = input.rotation(Rotation.Roll)
        basic.clearScreen()
    }
})
```

--- /task ---

--- task ---

Lorsque tu modifies un bloc de code dans le panneau de l'éditeur de code, le simulateur redémarrera.

**Teste ton programme**

+ Déplace-toi du centre du micro:bit vers la droite ou la gauche.

Les LED s'allumeront et resteront allumées pendant un court instant. **Garde ta souris immobile jusqu'à ce que les LED s'éteignent.**

+ Lorsque les LED s'éteignent, déplace-toi de la nouvelle position (ta position de repos) vers la droite ou vers la gauche à nouveau.

Les LED s'allumeront et resteront allumées **pendant un court instant**.

Répète ce processus pour vérifier que les LED ne s'allument que lorsqu'elles s'éloignent de la position de repos.

--- /task ---

### Laisser le micro:bit se reposer

Tu dois laisser au micro:bit le temps de se reposer avant de définir la nouvelle `positionRepos`{:class='microbitvariables'} sur la variable.

--- task ---

Modifie la valeur dans `pause`{:class='microbitbasic'} de `100` à `5 secondes`.

```microbit
let positionRepos = 0
let mouvements = 0
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < positionRepos - 10 || input.rotation(Rotation.Roll) > positionRepos + 10) {
        mouvements += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(5000)
        positionRepos = input.rotation(Rotation.Roll)
        basic.clearScreen()
    }
})
```

--- /task ---

--- task ---

**Teste ton programme**
+ Déplace-toi du centre du micro:bit vers la droite ou la gauche.

Les LED s'allumeront et resteront allumées pendant **5 secondes**. **Garde ta souris immobile jusqu'à ce que les LED s'éteignent.**

+ Lorsque les LED s'éteignent, déplace-toi de la nouvelle position (ta position de repos) vers la droite ou vers la gauche à nouveau.

Les LED s'allumeront et resteront de nouveau allumées pendant 5 secondes.

--- /task ---

Ensuite, tu vas utiliser l'événement d'appui sur le bouton `A+B` pour **réinitialiser** ton tracker de sommeil !
