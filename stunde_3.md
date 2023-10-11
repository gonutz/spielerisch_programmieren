Stunde 3
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

Das Quadrat bleibt bisher an der selben Stelle. Um es zu bewegen muss sich die
X-Position ändern. Die erste `100` im Aufruf `window.DrawRect(100, ...` ist die
X-Position. Anstelle eines festen Wertes brauchen wir eine **Variable**.

Variablen
---------

Eine Variable ist ein veränderbares Stück Speicher im Computer, dessen Wert wir
verändern können. Wir erweitern unser Programm:

```
package main

import "github.com/gonutz/prototype/draw"

func main() {
    x := 0
	draw.RunWindow("Recht Eckig", 800, 600, func(window draw.Window) {
		window.DrawRect(x, 100, 100, 100, draw.Red)
		x++
	})
}
```

Die neue Zeile `x := 0` stellt eine neue Variable mit dem Namen `x` her. Diese
repräsentiert die X-Position des Quadrats. Zu Beginn wird sie auf `0` gesetzt,
also ganz links an den Rand.

Unsere Funktion, in der wir `window.DrawRect` aufrufen, wird 60 mal pro Sekunde
aufgerufen. So oft wird der Bildschirm neu gezeichnet. Dazu sagen wir 60 Frames
pro Sekunde.

Die Zeile `x++` erhöht den Wert von `x` um eins. Das passiert in jedem Frame,
also 60 mal pro Sekunde. Daher sehen wir, dass sich das Quadrat mit 60 Pixeln
pro Sekunde nach rechts bewegt.

Y-Position ändern
-----------------

Um das Quadrat auch in Y-Richtung zu bewegen, nutzen wir eine Zufallszahl. Das
gibt dem Quadrat einen interessanten Weg durch das Fenster:

```
package main

import (
	"math/rand"

	"github.com/gonutz/prototype/draw"
)

func main() {
	x := 0
	y := 200
	draw.RunWindow("Recht Eckig", 800, 600, func(window draw.Window) {
		window.DrawRect(x, y, 100, 100, draw.Red)
		x++
		y += rand.Intn(9) - 4
	})
}
```

Das Quadrat wiederholen
-----------------------

Nachdem das Quadrat das Fenster nach rechts verlässt, wird es nicht mehr
angezeigt. Das passiert wenn die X-Position größer wird als das Fenster breit
ist. Diese Bedingung können wir mit einem `if` abfragen und darauf reagieren:

```
package main

import (
	"math/rand"

	"github.com/gonutz/prototype/draw"
)

func main() {
	x := 0
	y := 200
	draw.RunWindow("Recht Eckig", 800, 600, func(window draw.Window) {
		window.DrawRect(x, y, 100, 100, draw.Red)
		x++
		if x > 800 {
		    x = -100
		}
		y += rand.Intn(9) - 4
	})
}
```
