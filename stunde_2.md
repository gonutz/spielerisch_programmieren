Stunde 2
========

Das "Hello World" Programm aus der letzten Stunde hat Text auf der Konsole
(Kommandozeile) angezeigt. Jetzt soll ein Fenster mit grafischer Ausgabe
angezeigt werden.

Dazu legen wir im Windows Explorer einen neuen Ordner `graphics` an. In diesem
Ordner erstellen wir die Datei `main.go` mit folgendem Inhalt:

```
package main

import "github.com/gonutz/prototype/draw"

func main() {
	draw.RunWindow("Recht Eckig", 800, 600, func(window draw.Window) {
		window.DrawRect(100, 100, 100, 100, draw.Red)
	})
}
```

In unserer Kommandozeile (devenv.bat) begeben wir uns mit dem Befehl `cd` in
den eben angelegten Ordner `graphics`. Wir erstellen ein neues Go Module mit

    go mod init graphics

und anschließend laden wir die im Code importierte Bibliothek herunter mit

    go mod tidy

Im Ordner `graphics` finden wir jetzt zwei neue Dateien `go.mod` und `go.sum`.
Diese sind von den letzten zwei Befehlen generiert worden und sind notwendig,
weil wir nicht nur die Standardfunktionen von Go nutzen wollen, sonder die
Bibliothek unter der URL

    https://github.com/gonutz/prototype

Diese stellt Funktionen zum Anzeigen von Grafiken, zum Ausgeben von Sound und
zur Eingabe über Maus und Tastatur zur Verfügung.