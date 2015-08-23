# Kirby CMS Administratorhandbuch
**von Jannik Beyerstedt**, v1.0.0  
*als Ergänzung zum Benutzerhandbuch*


## Einführung:
Dieses Administratorhandbuch beschreibt etwas genauer den Aufbau von kirby und die manuellen Möglichkeiten.  
Es wird jedoch nicht die gesamte Programmierung von kirby-Seiten beschrieben. Für weitergehende Fragen oder Probleme [kontaktieren Sie mich](mailto:jannik@beyerstedt.de) doch bitte oder schauen Sie selbst in die (englischsprachige) [Dokumentation von kirby](http://getkirby.com).


## Updates *mit der Update-Seite*:
Um die kirby-Installation zu aktualisieren kann man die (unsichtbare) Seite "update" im panel auswählen. Diese hat im panel selbst erst einmal keine Funktion, dafür muss man auf "Seite öffnen" klicken. Dann öffnet sich eine Seite, die nur sichtbar ist, wenn man angemeldet ist und die Benutzergruppe Admin hat.

Über diese Seite können nun bash-scripte ausgeführt werden. Der Inhalt des Scripts, das ausgeführt wird, ist jeweils über den "ausführen"-Button zu sehen.  
**Diese Scripte sind kein Spielzeug! Bitte nur ausführen, wenn die Auswirkungen bekannt sind!**  

Für ein normales Update, das ich per Mail auch ankündige und dann vorher getestet habe, reicht der erste Button aus. Damit werden die kirby-Seite, kirby selbst und das panel, sowie alle Module aktualisiert. Danach wird dr cache geleert, damit die Seite neu generiert wird.
Bitte lesen Sie sich die Ausgabe des Scripts durch! Eine Meldung wie `Not currently on any branch` sollte bitte umgehend gemeldet werden.

## neue Benutzer:
Um einen neuen Benutzer anzulegen geht man im panel oben links auf diese drei waagerechten Striche und in diesem Menü auf "Benutzer".  
Hier können neue Benutzer angelegt werden. In der Standard-Installation gibt es nur zwei Benutzergruppen `admin` und `editor`. Der Admin kann dabei auch bei allen Benutzer die Passwörter setzen. Der Editor hat als einzige Einschränkung, dass er keine Benutzer bearbeiten oder anlegen kann.

## Konfiguration *in der config.php*:
Für einige weitergehende Konfigurationen gibt es die Datei `/site/config/config.php`, die aber mit einem FTP-Programm oder über die Komandozeile der Servers bearbeitet werden muss.  
Eingestellt werden dürfen nur folgende Attribute:

- `c::set('cache', true)` schaltet den cache an oder aus
- `c::set('ssl', true)` hiermit kann man die ganze Seite von http aus https umleiten.

Für alle weiteren Einstellungen bitte mich kontaktieren!


* * * * * *

## Tiefergehende Informationen:
In diesem Kapitel wird die grundlegende Struktur von kirby (oberflächlich) erklärt.

### die Struktur von kirby
In kirby wird der Inhalt ganz klar von den templates und damit der Funktion der Seite selbst getrennt. Der Inhalt liegt in dem Ordner `content`, alle Dateien zur Funktion der Seite in `site`, generische Bilder, wie Logos in `assets/images`.  
In `site/templates` gibt es nun verschiedene Vorlagen für verschiedene Seiten. 

### die Ordnerstruktur des Inhalts
Im Ordnr `content` wird jede Seite durch einen Ordner repräsentiert. Diese Ordner muss mindestens ein Textdokument (.txt) enthalten, das den Inhalt der Seite einthält. Den Aufbau dieser Datei erkläre ich hier nicht weiter, da das panel für dessen Manipulation da ist.  
Außerdem können in diesen Ordner Bilder und andere Dokuemente hochgeladen werden, die zu dieser Seite gehören.  
Der Titel der Seite, der auch angezeigt wird ist in dem Textdokument enthalten. Der Ordnername hat zwei Aufgaben. Zuerst bestimmt dieser unter welcher URL die Seite erreichbar ist, zum anderen wird der Ordnername zur Sortierung genutzt. Eine Nummer am Anfang heißt, dass die Seite sichtbar ist.

Wie wird nun das Template aus `site/template` ausgewählt? Dafür ist der Dateiname des Textdokuments mit dem Inhalt zuständig. Diese muss gleich dem auszuwählenden Template sein.

Bilder werden entweder über den Dateinamen sortiert oder es muss eine weitere Textdatei mit NameDerDatei.txt angelegt werden. Das sollte aber dem Panel überlassen werden.


Dies ist eine vereinfachte Ansicht. Teilweise haben die Textdateien auch einen Namen zu dem es gar kein Template gibt. Dieser dient dann der Steuerung des Panels oder diese Seite stellt nur eine Sektion einer anderen Seite dar, aber gar keine eigenständige Seite.
