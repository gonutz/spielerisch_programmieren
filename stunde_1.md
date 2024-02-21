Stunde 1
========

Sonderzeichen und Shortcuts (Tastenkombinationen) auf der Tastatur
------------------------------------------------------------------

     Shift  Gedrückt halten um Großbuchstaben zu schreiben
       !    Shift+1
       "    Shift+2
       (    Shift+8
       )    Shift+9
       {    Alt Gr+7
       }    Alt Gr+0
      Tab   Die Taste zwei über Shift, macht ein langes Leerzeichen
     Strg   `Steuerung`, gedrückt halten für Aktionen wie Speichern, Undo, ...
    Strg+S  Speichern
    Strg+C  Kopiert den markierten Text in die Zwischenablage
    Strg+V  Fügt den Text aus der Zwischenablage an der aktuellen Stelle ein.
    Strg+Z  Undo (letzte Aktion rückgängig machen)
    Strg+Y  Redo (zuletzt rückgängig gemachte Aktion wiederherstellen)

Das erste Programm
------------------

Nach dem Start von Gool wird das `hello_world` Projekt geöffnet. Dies ist der
Code:

```
package main

import "fmt"

func main() {
	fmt.Println("Hello World!")
}
```

Beim klick auf den `Start` Button erscheint in der Programm-Ausgabe der Text
`Hello World!` gefolgt von einem Zeilenumbruch.

Wir können hier auch mathematische Funktionen ausführen, z.B.

    fmt.Println(3 + 4*5)

gibt die Zahl `23` aus (Punktrechnung geht auch in Go vor Strichrechnung).
