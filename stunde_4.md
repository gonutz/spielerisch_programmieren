Stunde 4
========

Wir starten mit dem Programm aus Stunde 2:

```
package main

import "github.com/gonutz/prototype/draw"

func main() {
	draw.RunWindow("Recht Eckig", 800, 600, func(window draw.Window) {
		window.DrawRect(100, 100, 100, 100, draw.Red)
	})
}
```

In Stunde 3 haben wir das Quadrat bewegt indem wir mit Variablen seine X- und
Y-Position verändert haben. In dieser Stunde verwenden wir hierfür
Benutzer-Eingaben per Tastatur.

Position als Variablen
----------------------

Wie in Stunde 3 ersetzen wir zunächste die feste Position durch Variablen. Wir
benötigen eine Variable für die X-Position und eine für die Y-Position:

```
package main

import "github.com/gonutz/prototype/draw"

func main() {
    x := 100
    y := 100
	draw.RunWindow("Recht Eckig", 800, 600, func(window draw.Window) {
		window.DrawRect(x, y, 100, 100, draw.Red)
	})
}
```

Benutzer-Eingaben
-----------------

Wir beginnen damit, das Quadrat nach rechts zu bewegen wenn die rechte
Pfeiltaste gedrückt wird:

```
package main

import "github.com/gonutz/prototype/draw"

func main() {
    x := 100
    y := 100
	draw.RunWindow("Recht Eckig", 800, 600, func(window draw.Window) {
	    if window.IsKeyDown(draw.KeyRight) {
	        x++
	    }
		window.DrawRect(x, y, 100, 100, draw.Red)
	})
}
```

Solange wir die rechte Pfeiltaste gedrückt halten, bewegt sich das Quadrat
Pixel für Pixel nach rechts. Sobald wir die Taste loslassen, hält das Quadrat
an.

Wir sehen hier ein neues Schlüsselwort: `if`. If heißt auf Deutsch "wenn" oder
"falls". Der Code in einem If-Block wird nur dann ausgeführt wenn die
Bedingung, die hinter dem `if` steht, erfüllt erst.

In unserem Fall lautet die Bedingung `window.IsKeyDown(draw.KeyRight)`. Die
Funktion `IsKeyDown` prüft, ob die angegebene Taste - in diesem Fall
`draw.KeyRight`, also die rechte Pfeiltaste - in diesem Moment gedrückt ist.
Wenn die Taste gedrückt ist gibt die Funktion `true` zurück, das bedeutet
"wahr". Wenn die Taste nicht gedrückt ist, gibt die Funktion `false` zurück,
das bedeutet "falsch" oder "unwahr". Nur wenn die Bedingung `true` ist, wird
der Code in den geschweiften Klammern (`{}`) nach dem `if` ausgeführt.

Bei einem `if` teilt sich also der Programmablauf in zwei mögliche Pfade: der
Pfad wenn die Bedingung eintritt und der Pfad wenn sie nicht eintritt. Die
Zeile `x++` wird nur dann ausgeführt, wenn die Bedingung `true` ist. Was auf
jeden Fall ausgeführt wird ist die Zeile `window.DrawRect(x, y, 100, 100,
draw.Red)`, denn sie steht außerhalb des `if` und ist somit nicht Teil des
If-Blocks. Wir nehmen also sozusagen einen eventuellen Umweg wenn das `if`
ausgeführt wird, und kehren dann auf den "normalen" Weg zurück.

Bewegen in alle Richtungen
--------------------------

Um das Quadrat nicht nur nach rechts, sondern in alle vier Richtungen, bewegen
zu können, fragen wir jetzt alle Pfeiltasten ab und verändern `x` und `y`
entsprechend. Zu bemerken ist, dass wir bei der Taste `draw.KeyDown`, also
Pfeiltaste nach unten, `y++` ausführen, also `y` erhöhen, statt eins
abzuziehen. Das liegt daran, dass die Y-Achse unseres Fensters oben mit `0`
beginnt und nach unten größer wird. Im Gegensatz zum Koordinatensystem aus dem
Mathematikunterricht zeigt die Y-Achse hier also von oben nach unten. Die
X-Achse zeigt wie gewohnt von links nach rechts.

```
package main

import "github.com/gonutz/prototype/draw"

func main() {
    x := 100
    y := 100
	draw.RunWindow("Recht Eckig", 800, 600, func(window draw.Window) {
	    if window.IsKeyDown(draw.KeyRight) {
	        x++
	    }
	    if window.IsKeyDown(draw.KeyLeft) {
	        x--
	    }
	    if window.IsKeyDown(draw.KeyDown) {
	        y++
	    }
	    if window.IsKeyDown(draw.KeyUp) {
	        y--
	    }
		window.DrawRect(x, y, 100, 100, draw.Red)
	})
}
```
