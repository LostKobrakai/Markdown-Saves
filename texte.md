#Processwire

##Was ist Processwire

ProcessWire ist ein serverseitiges Open Source Content Management System (CMS) das in erster Linie zum Webpublishing entwickelt wurde, jedoch durch seine API auch für weitreichendere Zwecke benutzt werden kann. Denkbar sind E-Commerce oder auch Client-Relationship-Management Plattformen. Das System läuft mit PHP 5 und MySQL.

##Warum habe ich mich für Processwire entschieden

ProcessWire bietet dem Anwender ein solide aufgebautes CMS, dass sich durch einige Eigenheiten auszeichnet. Diese ermöglichen jedoch eine extrem steile Lernkurve für Einsteiger mit einem simplen und ebenso mächtigem System.

###Pages

ProcessWire strukturiert alle Inhalte, ganz im Gegenteil zu ähnlichen Systemen, auf "einer" Ebene: in Seiten. Im ersten Moment erscheind dieser Gedanke etwas abwägig, jedoch zeigt sich schnell wie effektiv dieses Vorgehen sein kann.

####Hierarchie

Daten werden im Seitenbaum hierarchisch abgelegt. Durch unbegrenzte Verschachtelung und verschiedenen Sortierungsfunktionen sind sie dort leicht zu organisieren. Sämtliche Daten sind außerdem an einem Ort und nicht in vielen Unterfunktionen versteckt oder gar nur in der Datenbank vorhanden.

####Alles ist gleich

Für den Umgang mit Daten muss man als Entwickler vergleichsweise wenig beachten. Da diese alle in Seiten gespeichert sind ist der Zugriff für jeden Datentyp der selbe. Wie man diesen dann ausgibt ist dabei dem Entwickler selbst überlassen.

####Custom Fields

Da alle Seiten in ProcessWire durch Templates erstellt werden, in denen der Nutzer selbst Inhaltsvorgaben bereitstellt, lassen sich Seiten individuell auf ihre Anwendungszwecke anpassen. Diese Templates bestehen wiederum aus einer Sammlung von verschiedenen Eingabefeldern. Dabei sind einem nur wenige Grenzen gesetzt. Von der einfachen Textzeile bis zu Seitenverknüpfungen lässt sich alles regeln, ähnlich dem Knotensystem von Drupal, jedoch wenige kompliziert. Somit lasses sich beispielsweise ohne großen Aufwand einer Kategorieseite ein Feld für eine Beschreibungen oder eine spezielle Hintergrundfarbe mitgeben. Falls doch eine gewünschte Aufgabe nicht realisiert werden kann, dann kann man auch über Module noch weitere Felder nachinstallieren. Die Kombination der Felder, Templates und Seiten geben dem Nutzer eine sehr gute Basis zur Verwaltung von Inhalten.

###API

ProcessWire basiert auf einer sehr flexiblen und leicht zu lernenden API. Die Struktur, die in vielen Teilen der bekannten JavaScript Bibiliothek jQuery ähnelt, macht es vorallem Frontend Entwicklern einfach ihre Wünsche in ProcessWire umzusetzten. Über zwei globale Variablen `$page` und `$pages`kann man auf sämtliche Daten der aktuellen oder aller anderere Seiten in ProcessWire zugreifen. Dabei lässt sich mit Selektoren wie beispielsweise `name=ryan` oder `template=blog` relativ einfach und verständlich die Suche eingrenzen. Ebenso von jQuery inspiriert ist die Möglichkeit zur Verkettung von API-Befehlen. Damit lassen sich Aufrufe wie `$pages->find("template=blog, name*=FAQ:)->first()->url` in einer Zeile kombinieren, was den Code, richtig eingesetzt, sehr viel leichter lesbar macht.

Der zweite große Vorteil der API im Vergleich zu anderen Systemen ist, dass zu 99% kein Markup ausgeliefert wird, sondern nur die Rohdaten. Somit kann man selbst bestimmen, für was die Daten genutzt werden. So lässt sich ein Einstellungsmenü für das Seitentheme wie jede andere Seite erstellen, jedoch werden die Einstellungen dann direkt über die API zu einem Stylesheet verarbeiten, auf exakt die selbe Art wie auch die HTML Daten generiert werden.

Neben den Vorteilen der API an sich, ist sie auch sehr gut dokumentiert, was nicht zuletzt auf die relativ wenigen nötigen Funktionen zurückzuführen ist.

##Praktische Anwendung

###Installation

####Vorraussetzungen
ProcessWire läuft auf Apache mit aktuellen Versionen von PHP und MySQL. Weitere Datenbanktypen werden zwar nicht unterstützt, aber diese werden generell eher selten genutzt, so dass von den meisten Serveranbietern auch eine MySQL Datenbank zur Verfügung steht.

> A Unix or Windows-based web server running Apache
> PHP version 5.2.4 or greater
> MySQL 5.0.15 or greater (later versions of 4.x may also work)
> Apache must have mod_rewrite enabled
> Apache must support .htaccess files
> PHP's bundled GD 2 library
> PHP should support mysqli
> Recommended but not required

Installation

Die Installation von ProcessWire verläuft sehr ähnlich zu anderen vergleichbaren Systemen. Es werden Berechtigungen gecheckt, die MySQL und Adminzugangsdaten abgefragt und das System aufgespielt.

Die ProcessWire Installation funktioniert über ein Webinterface, das mit dem Softwarepaket mitgeliefert wird. Beim ersten Aufruf des Stammverzeichnis wird man automatisch auf die Installationsseite weitergeleitet.

Vor der Installation wird man dazu aufgefordert den Ordner der vorinstallierten Webseite umzubenennen. Alternativ könnte man sich unter dem angegebenen Link auch alternative Voreinstellungen herunterladen. Angeboten werden im Moment ein vorgefertigter Blog und ein "Blank"-Profil, dass nur die minimalsten Voreinstellungen enthält und nur für Entwickler interessant ist.

Im ersten Schritt der Installation wird die Systemkompatibilität geprüft. Für die meisten Webserver sollte es hier keine Probleme geben. Die hier gezeigten Fehler entstanden aufgrund einer lokalen Installation. Die fehlenden Berechtigungen sind jedoch schnell behoben. Sollten noch andere Fehler angezeigt werden sollte man sich im Zweifelsfall die Systemadministratoren kontaktieren.

Sobald alles in Ordnung ist kann es weiter gehen zum nächsten Schritt:

Die MySQL Datenbankeinrichtung ist unerwartet schon Schritt 3. Hier sollten keinerlei Schwierigkeiten auftreten.

Den Administrator Account erstellen und man ist so gut wie fertig.

Man sollte in dem Masse der grünen und vermeintlich fertigen Balken nicht überlesen, dass aus Sicherheitsgründen noch einige Dateien und Ordner wieder gelöscht werden sollten. Desweiteren wird auf die Konfigurationsdatein hingewiesen, die noch erweiterterte Einstellungen nach der Installation bieten. Leider ist dort festzustellen, dass in der Standartinstallation nicht die optimalsten Sicherheitseinstellungen getroffen sind. Danach kann man sich nach der erfolgreichen Installation auf die neue Seite stürzen.

###Erstellung einer Beispielseite