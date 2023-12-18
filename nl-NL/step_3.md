### Verschillende rust hoofdposities

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

Op dit moment registreert de micro:bit een beweging wanneer de micro:bit **niet** waterpas is.

Voor dit project wordt de micro:bit onder een kussen geplaatst, omdat het oncomfortabel zou zijn om hem op je hoofd te dragen!

Wanneer je gaat liggen, zal het gewicht van je hoofd op je kussen waarschijnlijk de micro:bit laten draaien zodat deze niet volledig waterpas ligt.

Dit is de **rustpositie**. 

Je hoeft alleen een beweging vast te leggen als de micro:bit wegdraait van de rustpositie. 

</div>
</div>

### Controleer of er beweging naar LINKS is vanuit de rustpositie

Je moet weten of er een verschil is tussen de rustpositie en de huidige draaipositie.

--- task ---

Sleep vanuit het menu `Rekenen`{:class="microbitmath"} een blok `0 - 0`{:class="microbitmath"}.

Plaats het in de `-10` van het `<`{:class='microbitlogic'} vergelijkingsblok.

--- /task ---

--- task ---

Open het `Variabelen`{:class="microbitvariables"} menu en klik op **Maak een variabele**.

Geef je nieuwe variabele de naam `rustPositie`.

--- /task ---

--- task ---

Sleep vanuit het menu `Variabelen`{:class="microbitvariables"} het blok `rustPositie`{:class="microbitvariables"}.

Plaats het in de eerste `0` in het `0 - 0`{:class="microbitlogic"} blok.

--- /task ---

--- task ---

Verander de `0` rechts van de `-`{:class='microbitmath'} naar `10`.

Je code zou er als volgt uit moeten zien:

```microbit
let bewegingen = 0
basic.forever(function () {
    let rustPositie = 0
    if (input.rotation(Rotation.Roll) < rustPositie - 10 || input.rotation(Rotation.Roll) > 10) {
        bewegingen += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        basic.clearScreen()
    }
})
```

--- /task ---

### Controleer of er beweging naar RECHTS is vanuit de rustpositie

--- task ---

Sleep vanuit het menu `Rekenen`{:class="microbitmath"} een blok `0 + 0`{:class="microbitmath"}.

Plaats het in de `10` van het `>`{:class='microbitlogic'} vergelijkingsblok.

--- /task ---

--- task ---

Sleep vanuit het menu `Variabelen`{:class="microbitvariables"} nog een blok `rustPositie`{:class="microbitvariables"}.

Plaats het in de eerste `0` in het `0 + 0`{:class="microbitlogic"} blok.

--- /task ---

--- task ---

Verander de `0` rechts van de `+`{:class='microbitmath'} naar `10`.

Je code zou er als volgt uit moeten zien:

```microbit
let bewegingen = 0
basic.forever(function () {
    let rustPositie = 0
    if (input.rotation(Rotation.Roll) < rustPositie - 10 || input.rotation(Rotation.Roll) > rustPositie + 10) {
        bewegingen += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        basic.clearScreen()
    }
})
```

--- /task ---

### Stel na elke beweging een nieuwe rustpositie in

Elke keer dat de micro:bit naar een nieuwe rustpositie wordt gedraaid, moet je de huidige positie instellen als de nieuwe rustpositie, zodat je deze in je vergelijking kunt gebruiken.

--- task ---

Sleep vanuit het menu `Variabelen`{:class="microbitvariables"} een blok `stel in op`{:class="microbitvariables"}.

Plaats het onder het blok `pauzeer (ms)`{:class='microbitbasic'}.

--- /task ---

--- task ---

Dupliceer het `rotatie`{:class='microbitinput'} blok en plaats het in de `0` van het `stel in op`{:class='microbitvariables'} blok.

Je code zou er als volgt uit moeten zien:

```microbit
let rustPositie = 0
let bewegingen = 0
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < rustPositie - 10 || input.rotation(Rotation.Roll) > rustPositie + 10) {
        bewegingen += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(100)
        rustPositie = input.rotation(Rotation.Roll)
        basic.clearScreen()
    }
})
```

--- /task ---

--- task ---

Als je een wijziging aanbrengt in een codeblok in het bewerkingspaneel zal de simulator opnieuw starten.

**Test je programma**

+ Beweeg het midden van de micro:bit naar links of rechts.

De LED's zullen oplichten en een korte tijd branden. **Beweeg je muis niet totdat de LED's uitgaan.**

+ Als de LED's uitgaan, beweeg dan van de nieuwe positie (je rustpositie) weer naar rechts of links.

De LED's zullen oplichten en **een korte tijd** branden.

Herhaal dit proces om te controleren of de LED's alleen gaan branden als er beweging is vanuit de rustpositie.

--- /task ---

### Laat de micro:bit uitrusten

Je zou de micro:bit wat tijd moeten geven om te rusten voordat je de nieuwe `rustPositie`{:class='microbitvariables'} instelt op de variabele.

--- task ---

Wijzig de waarde in `pauzeer (ms)`{:class='microbitbasic'} van `100` naar `5 seconden`.

```microbit
let rustPositie = 0
let bewegingen = 0
basic.forever(function () {
    if (input.rotation(Rotation.Roll) < rustPositie - 10 || input.rotation(Rotation.Roll) > rustPositie + 10) {
        bewegingen += 1
        basic.showIcon(IconNames.Heart)
        basic.pause(5000)
        rustPositie = input.rotation(Rotation.Roll)
        basic.clearScreen()
    }
})
```

--- /task ---

--- task ---

**Test je programma**
+ Beweeg het midden van de micro:bit naar links of rechts.

De LED's zullen oplichten en **5 seconden** blijven branden. **Beweeg je muis niet totdat de LED's uitgaan.**

+ Als de LED's uitgaan, beweeg dan van de nieuwe positie (je rustpositie) weer naar rechts of links.

De LED's zullen oplichten en weer 5 seconden blijven branden.

--- /task ---

Vervolgens ga je de gebeurtenis `Wanneer knop A+B wordt ingedrukt` gebruiken om je slaapmonitor te **resetten**!
