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
Auch auf einem Klavier viel aus wie schnell das Stück gespielt werden soll also Legen wir zuerst eine Geswindigkeit fest mit der die Noten abgespielt werden sollen. Für das Lied Jingle Bells empfiehlt sich ein Tempo von 228 bpm.
```blocks
music.setTempo(228)
```
## ~@unplugged 
Starten wir mit den ersten Noten. <br>
![Noten](https://github.com/r00b1nh00d/Jinglebells/blob/master/JingleBellsNoten.png?raw=true) <br>
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




