# JingleBells
## ~avatar avatar @unplugged

"Oh, was für ein Spaß es ist, in einem Pferdeschlitten zu reiten und die Glocken den ganzen Weg lang klingeln"

## ~ @unplugged
Sicher hast du schon erraten, worum es hier geht :-) <br>
Richtig! Hier siehst du, wie du deinem Calliope den Klassiker Jingle Bells beibringst, denn dein Calliope kann auch etwas Musik spielen. <br>
Du musst es für ihn nur übersetzen. <br>
Hier wird dir gezeigt, wie du musikalische Noten für den Calliope programmierst. <br>
Besonders gut eignen sich dafür Klaviernoten. Auch wenn du diese nicht lesen kannst, kein Problem! Eine kleine Einführung gibt's mit dazu! 

## Schtitt 1
Auch auf einem Klavier macht es viel aus, wie schnell das Stück gespielt werden soll. Also legen wir zuerst eine Geschwindigkeit fest, mit der die Noten abgespielt werden sollen. Für das Lied Jingle Bells empfiehlt sich ein Tempo von 228 bpm.
```blocks
music.setTempo(228)
```
## ~@unplugged 
Starten wir mit den ersten Noten. <br>
![Noten](https://github.com/r00b1nh00d/Jinglebells/blob/master/JingleBellsNoten.png?raw=true) <br>
Einfache Erklärung zum Notenlesen: <br>
Ist hier ein Kreis ohne Füllung gezeichnet, nennt man dies "ganze Note" und spielt diese 4-Schläge lang. <br>
Ist an diesem Kreis ohne Füllung noch ein Strich gezeichnet, nennt man dies "halbe Note" und spielt diese 2-Schläge lang. <br>
Ist zusätzlich zum Strich der Kreis mit Füllung, nennt man dies "viertel Note" und spielt diese 1-Schläge lang. <br>
Ist jetzt noch ein Fähnchen am Strich gezeichnet, nennt man dies "achtel Note" und spielt diese 1/2-Schläge lang. <br>
In der letzten Zeile findest du noch eine Übersetzung, welcher Ton wo auf der Tonleiter sitzt. <br>

**Tipp**: am besten schreibst du dir die Noten und wie lang man diese schlägt jetzt in der richtigen Reihenfolge auf ein Blatt Papier.

## Schritt 2 
Um nicht ständig unser noch nicht fertiges Lied im Simulator zu hören, ziehen wir uns den ``||input:wenn Knopf A gedrückt||`` in den Arbeitsbereich. <br>
In diesen Block kommen unsere Blöcke ``||music: spiele Note||``
Beginnen wir mit der ersten "Zeile" Noten. <br>
Hier müssen nun einfach die Noten und Schläge eingetragen werden, welche du dir vorab herausgeschrieben hast. <br>
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
Diese erste Zeile kommt mehrmals in diesem Lied vor. Wenn sich in der Informatik Dinge einfach wiederholen, bietet sich eine Schleife an.

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
Die zweite und dritte Zeile kannst du sogar auch in die Schleife programmieren. Mithilfe einer ``||logic: wenn-dann-Bedingung||`` kannst du sicherstellen, dass die zweite und vierte Zeile zur richtigen Zeit abgespielt werden.
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


## @ ~ unplugged 
Du möchtest noch mehr Weihnachtslieder auf dem Calliope speichern? <br>
Kein Problem! <br>
Mit Hilfe der Wenn-Dann-Bedinugung kannst du eine Jukebox programmieren. <br> 
Dazu haben wir sogar ein Video für euch: !video[JukeBox](https://www.youtube.com/watch?v=K-27g-bg3Ac?raw=true)

