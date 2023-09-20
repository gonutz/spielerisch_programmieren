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
     Strg   Kurz für Steuerung, gedrückt halten für Aktionen wie Speichern, Undo, ...
    Strg+S  Speichern
    Strg+Z  Undo (letzte Aktion rückgängig machen)
    Strg+Y  Redo (zuletzt rückgängig gemachte Aktion wiederherstellen)

Das erste Programm
------------------

Das Programm zwischen den ``` Zeichen wird als Datei `hello.go` abgespeichert.
```
package main

import "fmt"

func main() {
	fmt.Println("Hello World!")
}
```

Entwicklungsumgebung
--------------------

Auf dieser Seite

    https://github.com/gonutz/devenv

kann man über diesen Direktlink

    https://github.com/gonutz/devenv/archive/refs/heads/main.zip

die Entwicklungsumgebung herunterladen. Diese wird in einen Ordner auf der Festplatte entpackt.
Dafür nach dem Download in den Download-Ordner auf der Festplatte wechseln, mit der Maus auf
die Datei `devenv-main.zip` rechtsklicken und "Alle extrahieren" klicken.

Wir gehen davon aus, dass der Ordner an die folgende Stelle entpackt wurde:

    C:\go\devenv-main

In diesem Ordner liegen die Unterordner `git`, `go`, `mingw`.
Außerdem liegt hier die Datei

    devenv.bat

Ein Doppelklick auf `devenv.bat` startet die Kommandozeile (auch Command Line oder Eingabaufforderung,
ein Fenster mit schwarzem Hintergrund).
In dieser Kommandozeile können dem Computer Kommandos befohlen werden, der Computer antwortet darauf.
Dabei geben wir Text ein und erhalten Text zurück.

Kommandos
---------

    cls         steht für Clear Screen, löscht den Bildschirm
    go version  führt das Programm go (den Go-Compiler) mit dem Parameter `version` aus
    cd          steht für Change Directory, wechselt den aktuellen Ordner

Um das oben geschriebene Programm zu starten, navigieren wir mit `cd` zum Ordner in dem die Datei liegt.
Wir gehen davon aus, dass wir `hello.go` in einem Ordner `hello_world` im Ordner `devenv-main` gespeichert
haben.

    cd C:\go\devenv-main\hello_world

Der Go-Compiler (das Programm `go`) macht aus unserem Text `hello.go` ein Programm das auf Windows
ausgeführt werden kann:

    go run hello.go

Go run macht aus dem Text ein Programm und führt es direkt danach aus.
Die Ausgabe des Programms lautet:

    Hello World!
