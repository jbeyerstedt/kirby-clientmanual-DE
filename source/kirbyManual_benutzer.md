# Kirby CMS Benutzerhandbuch
**von Jannik Beyerstedt**, v1.1.0  


## Einführung:
"kirby" ist ein dateibasiertes CMS, es können also alle Inhalte mit einem Texteditor und einem Dateibrowser bearbeitet werden. Für eine bequemere Bearbeitung gibt es jedoch eine Web-Bedienoberfläche, mit der (fast) alle Funktionen gesteuert werden können.  
Diese Bedienoberfläche heißt "panel" und wird in anderes Systemen auf als "backend" oder "Administrator-login" bezeichnet. In diesem Benutzerhandbuch wird der Umgang mit dem panel beschrieben, Details zu den Tiefen des Systems finden sich in meinem Adminitratorhandbuch.  
Ein weiterer Begriff ist das "frontend", welches den für den normalen Besucher sichtbaren Teil beschreibt, also die Webseite an sich.  
Für die hier beschriebenen URLs gilt, dass diese immer den Teil nach der Domain wiedergeben. Wenn also eine URL `/panel` heißt, muss `ihreDomain.de/panel` in  den Browser eingegeben werden.


## Das Panel:
Das Panel ist immer unter der URL `/panel` zu finden. Hier muss man sich zunächst mit einem vorhandenen Account anmelden um die Seite bearbeiten zu können.

Zuerst ist das sog. Dashboard zu sehen. Auf der linken Seite stehen immer die Seiten und Ordner der Webseite. Diese Module werden in den nächsten Kapiteln erklärt.

### Seiteneinstellungen/ Seitenvariablen
Die globalen Einstellungen der Webseite geben alle Informationen wieder, die auf der gesamten Webseite gebraucht werden. Das Menü dafür ist unter dem Knopf ganz oben links unter "Einstellungen" zu finden.

Die Felder sollten sich in der Regel selbst erklären, einige (vor allem die Metadaten) führe ich hier aber noch einmal auf:

- Titel der Webseite: Name im Tab des Browsers
- Autor: für Suchmaschinen
- Beschreibung: der kurze Text bei den Suchergebnissen von google und co

### die Seitenstruktur
In kirby gibt es erst einmal zwei Arten von Seiten: sichtbar und unsichtbar. Sichtbare Seiten werden bei meinen Webseiten dafür genutzt, dass diese in Menüs automatisch auftauchen.  
Dass eine Seite unsichtbar ist heißt nicht, dass diese nicht aufgerufen werden kann, sondern, dass diese dann per Hand verlinkt werden muss. Das sind z.B. Seiten wie die Error-Seite (wenn eine falsche URL aufgerufen wurde - dieser 404 Fehler) oder auch das Impressum, das meist in der Fußzeile verlinkt ist, aber nicht im Menü auftaucht.  
Sichbare Seiten können dann auch noch sortiert werden, um die Reihenfolge in den Menüs zu steuern. Das geht per drag and drop, wenn man auf "bearbeiten" über der Liste klickt.

* * * * * *

### neue Seite erstellen
Eine neue Seite kann mit dem "hinzufügen"-Knopf erstellt werden. Dafür muss ein Titel festgegelt werden, aus dem dann ein URL-Anhang gegeriert wird. Das ist der Teil, der dann in der URL-Zeile des Browsers steht. Dieses Feld wird automtisch so bearbeitet, dass die Regeln für URLs beachtet werden.  
Als letztes muss eine Vorlage ausgewählt werden. Diese regelt welche Funktion die Seite erfüllen soll und damit auch wie diese aussieht.

Eine neue Seite ist beim Erstellen immer erst einmal unsichtbar. Unter "bearbeiten" kann man dies ändern, indem man die Seite von rechts nach links zieht. Dabei kann auch direkt die Sortierung geändert werden.

### eine Seite bearbeiten
Erst einmal ein paar Worte zum prinzipiellen Vorgehen. Im nächsten Kapitel geht es dann darum, wie Texte formatiert werden können.  
Ein weiters Vorwort noch: Es kann sein, dass nicht auf allen Seiten alle Funktionen, die in den nächsten Abschnitten beschrieben werden, verfügbar sind. Das hat dann in der Regel auch einen tieferen Sinn, bei Zweifeln aber sonst einfach nachfragen.

Wenn man nun auf eine Seite klickt, sieht man eine zweigeteilte Ansicht. In der linken Leiste kann man wieder weitere Seiten hinzufügen, wie schon vom Dashboard bekannt. Außerdem können der Seite Dateien hinzugefügt werden. Diese werden dann - je nachdem wie Ihre Webseite gestaltet ist - automatisch angezeigt oder können im Text verlinkt werden.

Auf der rechten Seite kann der Inhalt der Seite bearbeitet werden. Je nachdem welche Vorlage gewäht wurde und wie die Seite gestaltet ist gibt es mehr oder weniger verschiedene Felder und Funktionen. Alle Seite haben jedoch einen Titel, der meist oben auf der Seite als Überschrift des Artikels (o.ä.) angezeigt wird. Außerdem ist dies meistens auch der Title, der im Menü verwendet wird.  
Danach gibt es den Haupttext, sowie evtl. weitere Textbereiche und Optionen. Diese sind dann aber mit selbsterklärenden Überschriften versehen.  
Alternativ kann eine Seite auch nur als "Ordner", also eine Sammlung von weiteren Seite zur Strukurierung der Inhalte dienen.

Nachdem man gespeichert hat, kann die Seite über den entsprechenden Knopf auf der linksen Seite geöffnet werden.

Teilweise werden Unterseiten auch dafür verwendet weitere Blöcke auf einer Seite zu strukturieren. Diese sind dann nicht einzeln sichtbar. Das wird dann aber einzeln erklärt.


* * * * * *

## Texte:
kirby verhält sich bei der Bearbeitung von Texten etwas anders als andere Textbearbeitungsprogramme, die Sie vielleicht kennen. Man kann nämlich nicht direkt die Schriftgröße und andere Texteinstellungen ändern. Dafür wird jedoch eine auf Webseite angepasste "Sprache" verendet, die "markdown" heißt. Das ist jetzt aber nicht so kompliziert, wie es vielleicht auf den ersten Blick wirkt, Sie müssen nicht programmieren können.  
Bei der Gestaltung von Webseiten ist es üblich das Aussehen der Text zentral festzulegen. Daher kann die Schriftgröße und von Überschriften und Text nicht einzeln festgelegt werden. Der Fließtext kann ganz normal aufgeschrieben werden, Überschriften müssen speziell gekennzeichnet werden. Um Texte gut strukturieren zu können gibt es sechs verschiedene Überschriften, in der Regel solten aber nur die Überschriften 3-5 verwendet werden, wobei die Überschrift 3 größte Überschrift für normale Texte ist. (Die Überschriften 1 und 2 sind für andere Zwecke reseviert.)  
Unter den unsichtbaren Seiten gibt es eine namens "z-Hilfe", die die Überschriften und die Markdown-Syntax auch noch einmal erklärt.

### Markdown
Die Elemente, die am häufigsten benötigt werden sind:

- Überschriften: `#` vor die Überschrift setzen. Anzahl entspricht dem Rang der Überschrift (Überschrift&nbsp;3&nbsp;=>&nbsp;`###`)
- Fettdruck: Den Text der fett geschreben werden soll in doppente Sternchen `**` setzen
- Kursivdruck: Den Text der fett geschreben werden soll in einfache Sternchen `*` setzen
- Listen: einfach `-` an den Anfang dr Zeile setzen. Jedoch vorher eine Zeile leer lassen  
Für nummerierte Listen muss man am Anfang der Zeile `1.` schreiben, die Reihenfolge der Nummern ist egal.
- Zeilenumbruch: einen einfache Zeilenumbruch erhält man durch eine neue Zeile
- Absatz: für einen Absatz hingegen muss man eine Zeile frei lassen

* * * * * *

### Kirbytags
Die Basis-Formatierungen von Markdown wurden in kirby noch um sog. Tags ersetzt:

Kirbytags haben immer eine einheitliche Form:  
`(name: Wert attribut: Wert_Attribut)`  
Eine normale runde Klammer leitet den Kirbytag ein. Danach folgt der Name des Tags und mit einem Doppelpunkt werden die Werte übergeben. Einige Kirbytags haben noch weitere Optionen, die durch weitere Paare aus Attribut-Name und Wert eingestellt werden. Diese sind wieder durch einen Doppelpunkt getrennt. Nun ein paar Beispiele:

- `(link: http://google.com text: Eine Suchmaschine popup:yes)`  
Für einen Link reicht das Ziel, dann wird als Text die URL angezeigt. Alternativ kann man einen eigenen Text hinzufügen. Außerdem kann man mit `popup:yes` festlegen, dass der Link in einem neuen Tab geöffnet werden soll.
- `(link: impressum)`  
Interne Links kann man auch erstellen lassen. In diesem Beispiel ohne speziellen Text.
- `<email@domain.de>` oder `(email: email@domain.de)`  
Für einen E-Mail-Link. Auch hier kann ein eigener Text für den Fließtext definiert werden wie `text: kontaktieren Sie mich`.
- `(image: bildname.jpg)`  
Um ein Bild in den Text einzufügen, das vorher in dieser Seite hochgeladen wurde (muss links unter "Dateien" auftauchen)
- `(file: download.pdf)`  
Um eine Datei in den Text einzufügen. Auch hier kann man wieder einen Text festlegen.

Es gibt noch viele weitere Möglichkeiten, dies sind aber die gängigsten. Bei manchen Seiten habe ich noch weitere Kirytags geschrieben oder installiert. Diese sind dann auch in der `x-Hilfe`-Seite zu finden.
