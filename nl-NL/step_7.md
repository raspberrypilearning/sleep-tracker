## 1,2,3, slapen!

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

Tellen wordt soms gebruikt als een manier om in slaap te vallen.

In deze stap ga je een reeks getallen weergeven vóór de zZs animatie wanneer het programma start.

</div>
</div>

Je kunt een timer maken van 1 tot 3 met behulp van een `voor`{:class='microbitloops'} lus.

--- task ---

Sleep vanuit het blokmenu `Lussen`{:class='microbitloops'} een blok `voor index`{:class='microbitloops'}.

Plaats het in het `functie zZ`{:class='microbitfunctions'} blok, boven het `keer herhalen`{:class='microbitloops'} blok.

Verander de `4` naar `2`.

--- /task ---

--- task ---

Vanuit het `Basis`{:class='microbitbasic'} blokmenu, sleep je een `toon nummer`{:class='microbitbasic'} blok.

Plaats het in het `voor index`{:class='microbitloops'} blok.

--- /task ---

--- task ---

Sleep vanuit het blokmenu `Basis`{:class='microbitbasic'} een blok met `pauzeer (ms)`{:class='microbitbasic'}.

Plaats het in het `voor index`{:class='microbitloops'} blok, onder het `toon nummer`{:class='microbitbasic'} blok.

Verander de `100` naar `1 seconde`.

--- /task ---

Toen je het `voor index`{:class='microbitloops'} blok aan je Werkruimte toevoegde, werd de `index`{:class='microbitvariables'} variabele gemaakt.

De variabele `index`{:class='microbitvariables'} neemt elke waarde aan van `0` tot `2` (het eindgetal in ons voorbeeld) en telt elke keer met één op.

Hernoem de `index`{:class='microbitvariables'} variabele naar `seconde` omdat je timer elke seconde stijgt.

--- task ---

Klik op de pijl rechts van de `index`{:class='microbitvariables'} variabele en selecteer `Naam van variabele wijzigen.....`.

Vervang de tekst `index` met `seconde` en klik `Ok`.

--- /task ---

--- task ---

Sleep vanuit het menu `Variabelen`{:class="microbitvariables"} een variabele `seconde`{:class="microbitvariables"}.

Plaats het in de `0` van het `toon nummer`{:class='microbitbasic'} blok.

--- /task ---

--- task ---

**Test je programma**

+ De LED's geven `0`, vervolgens `1` vervolgens `2` weer, met een pauze van één seconde ertussen.

--- /task ---

Het is logischer "1, 2, 3” te zien dan "0, 1, 2”.

We kunnen dit doen met wat eenvoudige wiskunde.

--- task ---

Sleep vanuit het menu `Rekenen`{:class="microbitmath"} een blok ` + `{:class="microbitmath"}.

Plaats het in het `toon nummer`{:class='microbitbasic'} blok, zodat het de `seconde`{:class='microbitvariables'} variabele vervangt.

--- /task ---

De `seconde`{:class='microbitvariables'} variabele wordt weggedrukt, maar je kunt hem nog steeds gebruiken.

--- task ---

Sleep de `seconde`{:class='microbitvariables'} variabele naar de eerste `0` in het `+`{:class='microbitmath'} blok.

Verander de tweede `0` in `1`.

--- /task ---

Dit zijn de blokken die in deze stap zijn gewijzigd:

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

**Test je programma**

+ De LED's geven `1`, vervolgens `2` vervolgens `3` weer, met een pauze van één seconde ertussen.

--- /task ---

--- task ---

Download je programma naar de micro:bit!

--- /task ---

[[[download-to-microbit]]]

Goed gedaan! Je hebt nu een volledig werkende slaapmonitor!

Nu is het tijd om te kijken wat je hebt geleerd!
