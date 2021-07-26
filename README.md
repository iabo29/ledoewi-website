# ledoewi-website

Repository für die Website https://dorf.wichmar.eu

## How-to

### Allgemeines

Die Seite wird mit Jekyll gebaut. Einzelne Seiten können mit Markdown oder HTML geschrieben werden. Am Anfang jeder Seite ist ein sog. YAML-Block, in dem bestimmte Variablen gespeichert werden. Nach jeder Änderung wird die Seite dann neu zusammengebaut. Oben im Github-Repository erscheint dann ein grünes Häkchen (falls es geklappt hat) oder ein rotes Kreuz (falls was schiefgegangen ist).

* Markdown-Guide https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
* Bilder können in den Ordner `/assets/images/` gespeichert werden
* Bilder bitte so einfügen (sonst siehts doof aus):
```
{% include image.html link="/assets/images/tollesBild.png" %}
```

### Seiten editieren

Seiten können relativ simpel verändert werden. Dazu einfach die entsprechende Markdown-Datei im Wurzelverzeichnis editieren. Die Seiten von den Veranstaltungen sind im Ordner `veranstaltungen`. Die Einträge auf der Startseite sind im Ordner `_posts`.

### Etwas auf die Startseite schreiben

* Einträge auf der Startseite sind im Ordner `/_posts`
* Dort eine neue Datei anglegen `yyyy-mm-dd-neuigkeit.md`
* YAML-Block schreiben
```
---
title: Titel der Neuigkeit
layout: post
datum: Datum, das angezeigt werden soll
image: Optional, falls ein Bild mit angezeigt werden soll. Falls ja, hier der link rein, z.b. /assets/images/neuesBild.jpeg. Falls nicht, das Feld weglassen
---
```
* Losschreiben. 

### Eine neue Seite anlegen

* Seite im Wurzelverzeichnis anlegen `neueSeite.md` oder `neueSeite.html`
* YAML-Block schreiben
```
title: Titel der Seite
layout: einfach
```
* `layout: einfach` generiert eine Simple Seite, wo Dinge auf dem weißen transparenten Hintergrund zu sehen sinf
* `layout: default` lässt mehr Handlungsspielraum. Ein weißer container kann z.B. erstellt werden mit:
```
<div class="container>
...
</div>
```
* Inhalt schreiben (markdown oder HTML)
* Wenn die Seite im Menü oben erscheinen soll, dann die Datei `_data/navigation.yaml` editieren
* Wenn die Seite im Menü unter 'Veranstaltungen' stehen soll, dann im YAML-Block oben folgende Zeile hinzufügen
```
kategorie: Veranstaltung
```

### Für Fortgeschrittene

Die Seite verwendet die Bootstrap-Bibliothek, die das ganze Design ermöglicht. Einen Überblick, was alles möglich ist, gibt es hier: https://getbootstrap.com/docs/4.0/components Das meiste kann man problemlos von dort rüberkopieren und ins HTML-Dokument einfügen.

Generell können Seiten entweder in Markdown oder in HTML geschrieben werden. Es empfiehlt sich, die Seiten in Markdown zu schreiben. Kompliziertere Elemente, die HTML benötigen, können trotzdem eingefügt werden. Dazu schreibt man den HTML-Block in eine eigene Datei (z.B. `TollesLayout.html`) und speichert den im Ordner `_includes` ab. Im Markdown-Dokument kann der dann mit der Zeile
```
{% include TollesLayout.html %}
```
eingefügt werden. Eine ausführliche Dokumentation von Jekyll (das Skript, welches die Seite zusammenbastelt) gibt es hier: https://jekyllrb.com/docs/step-by-step/01-setup/

