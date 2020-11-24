# JingleBells
## ~avatar avatar @unplugged


## ~ @unplugged

"Oh, was für ein Spaß es ist, in einem Pferdeschlitten zu reiten und die Glockeln den ganzen Weg lang klingeln"

## ~ @unplugged
Sicher hast du schon erraten worum es hier geht :-) <br>
Richtig! Hier siehst du wie du deinem Calliope den Klassiker Jingle Bells beibringst
Denn dein Calliope kann auch etwas Musik spielen, du musst es nur ein wenig für ihn Übersetzen. <br>
Hier wird dir gezeigt, wie du musikalische Noten für den Calliope programmierst. <br>
Besonders gut eignen sich dafür Klaviernoten. Auch wenn du diese nicht lesen kannst kein Problem! Eine kleine Einführung gibts mit dazu! 

## Schtitt 1
Auch auf einem Klavier viel aus wie schnell das Stück gespielt werden soll also Legen wir zuerst eine Geswindigkeit fest mit der die Noten abgespielt werden sollen. 
```blocks
music.setTempo(228)
```
## ~@unplugged 
Starten wir mit den ersten Noten. <br>
[NotenBild]
Einfache erklärung zum Notenlesen: <br>
Ist hier ein Kreis ohne Füllung gezeichnet nennt man dies "ganze Note" und spielt diese 4-Schläge lang. <br>
Ist an diesem Kreis ohne Füllung noch ein Strich gezeichnet nennt man dies "halbe Note" und spielt diese 2-Schläge lang. <br>
Ist zusätzlich zum Strich der Kreis mit Füllung  nennt man dies "viertel Note" und spielt diese 1-Schläge lang. <br>
Ist jetzt noch ein Fähnchen am Strich nennt man dies "achtel Note" und spielt diese 1/2-Schläge lang. <br>
In der letzten Zeile findes du noch eine Übersetzung welcher Ton wo auf der Tonleiter sitzt. <br>

**Tipp**: am besten schreibst du dir die Noten und wie lang man diese schlägt jetzt in der richtigen Reihenfolge auf ein Blatt Papier.

## Schritt 2 
Um nicht ständig unser noch nicht fertiges Lied im Simulator zu hören ziehen wir uns den ``||input:wenn Knopf A gedrückt||`` in den Arbeitsbereich. <br>
In diesen Block kommen unsere Blöcke ``||music: spiele Note||``
Beginnen wir mit der ersten "zeile" Noten. <br>
Hier müssen nun einfach die Noten und Schläge eingetragen werden, welche du dir vorab heraus geschrieben hast. <br>
```blocks
input.onButtonPressed(Button.A, function () {
    music.playTone(330, music.beat(BeatFraction.Whole))
    music.playTone(330, music.beat(BeatFraction.Whole))
    music.playTone(330, music.beat(BeatFraction.Double))
    music.playTone(330, music.beat(BeatFraction.Whole))
    music.playTone(330, music.beat(BeatFraction.Whole))
    music.playTone(330, music.beat(BeatFraction.Double))
    music.playTone(330, music.beat(BeatFraction.Whole))
    music.playTone(392, music.beat(BeatFraction.Whole))
    music.playTone(262, music.beat(BeatFraction.Whole))
    music.playTone(294, music.beat(BeatFraction.Whole))
    music.playTone(330, music.beat(BeatFraction.Breve))
})
```


## Schritt 3 
Diese erste Zeile kommt nochmal genau so in diesem Lied vor. Wenn sich in der Informatik Dinge einfach widerholen bietet sich eine Schleife an.

```blocks
input.onButtonPressed(Button.A, function () {
for (let index = 0; index <= 1; index++) {
    music.playTone(330, music.beat(BeatFraction.Whole))
    music.playTone(330, music.beat(BeatFraction.Whole))
    music.playTone(330, music.beat(BeatFraction.Double))
    music.playTone(330, music.beat(BeatFraction.Whole))
    music.playTone(330, music.beat(BeatFraction.Whole))
    music.playTone(330, music.beat(BeatFraction.Double))
    music.playTone(330, music.beat(BeatFraction.Whole))
    music.playTone(392, music.beat(BeatFraction.Whole))
    music.playTone(262, music.beat(BeatFraction.Whole))
    music.playTone(294, music.beat(BeatFraction.Whole))
    music.playTone(330, music.beat(BeatFraction.Breve))
    }
})
```
## Schritt 4
Die zweite und dritte Zeile kannst du sogar auch in die Schleife Programmieren. Mithilfe einer ``||logic: wenn-dann-bedingung||`` kannst du sicherstellen, dass die zweite und vierte Zeile zur richtigen Zeit abgespielt wird.
```blocks

input.onButtonPressed(Button.A, function () {
   
    for (let index = 0; index <= 1; index++) {
        music.playTone(330, music.beat(BeatFraction.Whole))
        music.playTone(330, music.beat(BeatFraction.Whole))
        music.playTone(330, music.beat(BeatFraction.Double))
        music.playTone(330, music.beat(BeatFraction.Whole))
        music.playTone(330, music.beat(BeatFraction.Whole))
        music.playTone(330, music.beat(BeatFraction.Double))
        music.playTone(330, music.beat(BeatFraction.Whole))
        music.playTone(392, music.beat(BeatFraction.Whole))
        music.playTone(262, music.beat(BeatFraction.Whole))
        music.playTone(294, music.beat(BeatFraction.Whole))
        music.playTone(330, music.beat(BeatFraction.Breve))
        if (index == 0) {
            music.playTone(349, music.beat(BeatFraction.Whole))
            music.playTone(349, music.beat(BeatFraction.Whole))
            music.playTone(349, music.beat(BeatFraction.Whole))
            music.playTone(349, music.beat(BeatFraction.Whole))
            music.playTone(349, music.beat(BeatFraction.Whole))
            music.playTone(330, music.beat(BeatFraction.Whole))
            music.playTone(330, music.beat(BeatFraction.Whole))
            music.playTone(330, music.beat(BeatFraction.Half))
            music.playTone(330, music.beat(BeatFraction.Whole))
            music.playTone(294, music.beat(BeatFraction.Whole))
            music.playTone(294, music.beat(BeatFraction.Whole))
            music.playTone(330, music.beat(BeatFraction.Whole))
            music.playTone(294, music.beat(BeatFraction.Double))
            music.playTone(392, music.beat(BeatFraction.Double))
        }
        if (index == 1) {
            music.playTone(349, music.beat(BeatFraction.Whole))
            music.playTone(349, music.beat(BeatFraction.Whole))
            music.playTone(349, music.beat(BeatFraction.Whole))
            music.playTone(349, music.beat(BeatFraction.Whole))
            music.playTone(349, music.beat(BeatFraction.Whole))
            music.playTone(330, music.beat(BeatFraction.Whole))
            music.playTone(330, music.beat(BeatFraction.Whole))
            music.playTone(330, music.beat(BeatFraction.Half))
            music.playTone(392, music.beat(BeatFraction.Whole))
            music.playTone(392, music.beat(BeatFraction.Whole))
            music.playTone(349, music.beat(BeatFraction.Whole))
            music.playTone(294, music.beat(BeatFraction.Whole))
            music.playTone(262, music.beat(BeatFraction.Double))
        }
    }
})
```




> Diese Seite bei [https://r00b1nh00d.github.io/jinglebells/](https://r00b1nh00d.github.io/jinglebells/) öffnen

## Als Erweiterung verwenden

Dieses Repository kann als **Erweiterung** in MakeCode hinzugefügt werden.

* öffne [https://makecode.calliope.cc/](https://makecode.calliope.cc/)
* klicke auf **Neues Projekt**
* klicke auf **Erweiterungen** unter dem Zahnrad-Menü
* nach **https://github.com/r00b1nh00d/jinglebells** suchen und importieren

## Dieses Projekt bearbeiten ![Build Status Abzeichen](https://github.com/r00b1nh00d/jinglebells/workflows/MakeCode/badge.svg)

Um dieses Repository in MakeCode zu bearbeiten.

* öffne [https://makecode.calliope.cc/](https://makecode.calliope.cc/)
* klicke auf **Importieren** und dann auf **Importiere URL**
* füge **https://github.com/r00b1nh00d/jinglebells** ein und klicke auf Importieren

## Blockvorschau

Dieses Bild zeigt den Blockcode vom letzten Commit im Master an.
Die Aktualisierung dieses Bildes kann einige Minuten dauern.

![Eine gerenderte Ansicht der Blöcke](https://github.com/r00b1nh00d/jinglebells/raw/master/.github/makecode/blocks.png)

#### Metadaten (verwendet für Suche, Rendering)

* for PXT/calliopemini
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
