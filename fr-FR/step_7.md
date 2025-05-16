## 1,2,3, dodo !

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

Le comptage est parfois utilisé comme moyen de s’endormir.

Dans cette étape, tu afficheras une séquence de nombres avant l'animation zZ au démarrage du programme.

</div>
</div>

Tu peux créer un minuteur qui compte de 1 à 3 en utilisant une boucle `pour`{:class='microbitloops'}.

--- task ---

Dans le menu des blocs `Boucles`{:class='microbitloops'}, fais glisser un bloc `pour index`{:class='microbitloops'}.

Place-le à l'intérieur du bloc `fonction zZ`{:class='microbitfunctions'}, au-dessus du bloc `répéter`{:class='microbitloops'}.

Remplace le `4` par `2`.

--- /task ---

--- task ---

Dans le menu des blocs `Base`{:class='microbitbasic'}, fais glisser un bloc `montrer nombre`{:class='microbitbasic'}.

Place-le à l'intérieur du bloc `pour index`{:class='microbitloops'}.

--- /task ---

--- task ---

Dans le menu des blocs `Base`{:class='microbitbasic'}, fais glisser un bloc `pause`{:class='microbitbasic'}.

Place-le à l'intérieur du bloc `pour index`{:class='microbitloops'}, sous le bloc `montrer nombre`{:class='microbitbasic'}.

Modifie le `100` par `1 seconde`.

--- /task ---

Lorsque tu as ajouté le bloc `pour index`{:class='microbitloops'} à ton espace de travail, la variable `index`{:class='microbitvariables'} a été créée.

La variable `index`{:class='microbitvariables'} prend sur chaque valeur de `0` à `2` (le nombre final dans notre exemple) et compte un par un.

Renomme la variable `index`{:class='microbitvariables'} `seconde` car ton minuteur augmentera chaque seconde.

--- task ---

Clique sur la flèche à droite de la variable `index`{:class='microbitvariables'} et sélectionne `Renommer la variable`.

Remplace le texte `index` par `seconde` et clique sur `Ok`.

--- /task ---

--- task ---

Dans le menu des blocs `Variables`{:class='microbitvariables'}, fais glisser une variable `seconde`{:class='microbitvariables'}.

Place-le dans le `0` du bloc `montrer nombre`{:class='microbitbasic'}.

--- /task ---

--- task ---

**Teste ton programme**

+ Les LED afficheront `0` puis `1` puis `2` avec une pause d'une seconde entre chaque.

--- /task ---

Il est plus naturel de voir "1, 2, 3" que "0, 1, 2".

Pour ce faire, il suffit d'effectuer quelques calculs simples.

--- task ---

Dans le menu des blocs `Maths`{:class='microbitmath'}, fais glisser un bloc `+`{:class='microbitmath'}.

Place-le dans le bloc `montrer nombre`{:class='microbitbasic'}, en remplaçant la variable `seconde`{:class='microbitvariables'}.

--- /task ---

La variable `seconde`{:class='microbitvariables'} sera supprimée, mais tu peux toujours l'utiliser.

--- task ---

Fais glisser la variable `seconde`{:class='microbitvariables'} vers le premier `0` dans le bloc `+`{:class='microbitmath'}.

Remplace le deuxième `0` par `1`.

--- /task ---

Voici les blocs qui ont changé à cette étape :

```microbit
function zZ () {
    for (let second = 0; second <= 2; second++) {
        basic.showNumber(second + 1)
        basic.pause(1000)
    }
    for (let index = 0; index < 2; index++) {
        basic.showLeds(`
            . . . . .
            . . . . .
            # # # . .
            . # . . .
            # # # . .
            `)
        basic.showLeds(`
            . . . . .
            # # # # .
            . . # . .
            . # . . .
            # # # # .
            `)
        basic.showLeds(`
            # # # # #
            . . . # .
            . . # . .
            . # . . .
            # # # # #
            `)
    }
}
```

--- task ---

**Teste ton programme**

+ Les LED afficheront désormais `1` puis `2` puis `3` avec une pause d'une seconde entre chacune.

--- /task ---

--- task ---

Télécharge ton programme sur ton micro:bit !

--- /task ---

[[[download-to-microbit]]]

Bien joué ! Tu as maintenant un tracker de sommeil entièrement fonctionnel !

Ensuite, il est temps de vérifier ce que tu as appris !
