#Processwire

##Was ist Processwire

ProcessWire ist ein serverseitiges Open Source Content Management System (CMS) das in erster Linie zum Webpublishing entwickelt wurde, jedoch durch seine API auch für weitreichendere Zwecke benutzt werden kann. Denkbar sind E-Commerce oder auch Client-Relationship-Management Plattformen. Das System läuft mit PHP 5 und MySQL.

##Warum habe ich mich für Processwire entschieden

ProcessWire bietet dem Anwender ein solide aufgebautes CMS, dass sich durch einige Eigenheiten auszeichnet. Diese ermöglichen jedoch eine extrem steile Lernkurve für Einsteiger bei einem simplen und ebenso mächtigem System.

###Pages

ProcessWire strukturiert alle Inhalte, ganz im Gegenteil zu ähnlichen Systemen, auf *einer* Ebene: in Seiten. Im ersten Moment erscheind dieser Gedanke etwas abwägig, jedoch zeigt sich schnell wie effektiv dieses Vorgehen sein kann.

####Hierarchie

Einzelne Seiten werden im Seitenbaum hierarchisch abgelegt. Diese können dort öffentlich sein und somit auf der Webseite angezeigt werden oder aber versteckt um nur als Speicherplatz zu dienen. Durch unbegrenzte Verschachtelung und verschiedenen Sortierungsfunktionen sind sie dort leicht zu organisieren. Sämtliche Daten sind außerdem an einem Ort und nicht in vielen Unterfunktionen versteckt oder gar nur in der Datenbank vorhanden.

####Alles ist gleich

Für den Umgang mit Daten muss man als Entwickler vergleichsweise wenig beachten. Da diese alle in Seiten gespeichert sind ist der Zugriff für jeden Datentyp der selbe. Wie man diesen dann ausgibt ist dabei dem Entwickler selbst überlassen.

####Custom Fields

Da alle Seiten in ProcessWire durch Templates erstellt werden, in denen der Nutzer selbst Inhaltsvorgaben bereitstellt, lassen sich Seiten individuell auf ihre Anwendungszwecke anpassen. Diese Templates bestehen wiederum aus einer Sammlung von verschiedenen Eingabefeldern. Dabei sind einem nur wenige Grenzen gesetzt. Von der einfachen Textzeile bis zu Seitenverknüpfungen lässt sich alles regeln, ähnlich dem Knotensystem von Drupal, jedoch wenige kompliziert. Somit lasses sich beispielsweise ohne großen Aufwand einer Kategorieseite ein Feld für eine Beschreibungen oder eine spezielle Hintergrundfarbe mitgeben. Falls doch eine gewünschte Aufgabe nicht realisiert werden kann, dann kann man auch über Module noch weitere Felder nachinstallieren. Die Kombination der Felder, Templates und Seiten geben dem Nutzer eine sehr gute Basis zur Verwaltung von Inhalten.

###API

ProcessWire basiert auf einer sehr flexiblen und leicht zu lernenden API. Die Struktur, die in vielen Teilen der bekannten JavaScript Bibiliothek jQuery ähnelt, macht es vorallem Frontend Entwicklern einfach ihre Wünsche in ProcessWire umzusetzten. Über zwei globale Variablen `$page` und `$pages`kann man auf sämtliche Daten der aktuellen oder aller anderere Seiten in ProcessWire zugreifen. Dabei lässt sich mit Selektoren wie beispielsweise `name=ryan` oder `template=blog` relativ einfach und verständlich die Suche eingrenzen. Ebenso von jQuery inspiriert ist die Möglichkeit zur Verkettung von API-Befehlen. Damit lassen sich Aufrufe wie `$pages->find("template=blog, name*=FAQ:)->first()->url` in einer Zeile kombinieren, was den Code, richtig eingesetzt, sehr viel leichter lesbar macht.

Der zweite große Vorteil der API im Vergleich zu anderen Systemen ist, dass zu 99% kein Markup ausgeliefert wird, sondern nur die Rohdaten. Somit kann man selbst bestimmen, für was die Daten genutzt werden. So lässt sich ein Einstellungsmenü für das Seitentheme wie jede andere Seite erstellen, jedoch werden die Einstellungen dann direkt über die API zu einem Stylesheet verarbeiten, auf exakt die selbe Art wie auch die HTML Daten generiert werden.

Neben den Vorteilen der API an sich, ist sie auch sehr gut dokumentiert, was nicht zuletzt auf die relativ wenigen nötigen Funktionen zurückzuführen ist.

###Sonstige Eigenschaften

####Theming

ProcessWire verwendet, wie an der API schon zu erkennen war PHP Templates für das Theming. Dabei ist zu beachten, dass in ProcessWire das Wort Template für 2 Dinge benutzt wird. Einerseits ist ein Template eine Zusammenstellung vieler Datenfelder im Backend und Vorlage für Seiten, andereseits die Datei in der die Daten aus den Datenfeldern in die HTML-Vorlage übertragen werden. Das ganze ist jedoch trotzdem Sinnvoll, da jedes Seitentemplate im Adminmenü, dass später auf der Webseite angezeigt werden soll, auch eine gleichnamige Templatedatei besitzen muss.

####Module

Module sind das Herzstück von ProcessWire. Das System besteht selbst aus vielen Modulen und somit sind selbst Kernelemente mit Modulen veränderbar. Bei der Installation mitgeliefert werden unter anderem Module zum Aufbau mehrsprachiger Seiten oder auch ein Caching-Modul. Wem die Funktionen von ProcessWire dann zu eingeschränkt sind, oder wenn man sich bestimmte Arbeitsabläufe erleichtern will, dann gibt es die Möglichkeit mit einer ähnlichen API, wie der zum Theming, Module zu erstellen. Einige Module sind auch auf der Webseite von ProcessWire zu finden, jedoch ist die Auswahl im Vergleich zu den großen Konkurrenten eher beschränkt.

####Rechtemanagement

ProcessWire besitzt ein solides Rechtemanagement, in dem sich nach ähnlichem Prinzip wie auch bei den Pages Nutzerrollen erstellen lassen. Dazu hat man die Möglichkeit Nutzerrechte zu definieren, diese zu verschiedenen Rollen zu kombinieren und dann einzelnen Nutzern zuzuweisen. Diese muss man jedoch selbst erstellen, da standartgemäß nur die Rollen `guest` und `Admin` definiert sind.

####Community

Da ProcessWire doch eine eher kleine Nutzerbasis hat ist es um so erstaunlicher wie gut die Community funktioniert. Der Entwickler *Ryan Cramer* steht mit einem kleinem Team an Moderatoren im eigenem Forum mit Rat und Tat zur Seite und hilft Einsteigern, wie auch erfahrenen Leuten bei ihren Problemen. Dabei ist er auch immer offen für Vorschläge und Verbesserungen für das CMS.

##Praktische Anwendung

###Installation

####Vorraussetzungen
ProcessWire läuft auf Apache mit aktuellen Versionen von PHP und MySQL. Weitere Datenbanktypen werden dabei nicht unterstützt.

> Ein Unix oder Windows Webserver mit Apache
> PHP Version 5.2.4 oder neuer
> MySQL 5.0.15 oder neuer
> mod_rewrite muss aktiviert sein
> .htaccess Daten müssen nutzbar sein
> Die GD 2 Bibliothek muss in PHP installiert sein
> PHP sollte mysqli unterstützen, ist jedoch nicht nötig

####Installation

Die Installation von ProcessWire verläuft sehr ähnlich zu anderen vergleichbaren Systemen. Es werden Berechtigungen gecheckt, die MySQL und Adminzugangsdaten abgefragt und das System aufgespielt.

#####Start

Die ProcessWire Installation funktioniert über ein Webinterface, das mit dem Softwarepaket mitgeliefert wird. Beim ersten Aufruf des Stammverzeichnis wird man automatisch auf die Installationsseite weitergeleitet.

#####Schritt 1: Seitenvoreinstellungen wählen

Vor der Installation wird man dazu aufgefordert den Ordner der vorinstallierten Webseite umzubenennen. Alternativ könnte man sich unter dem angegebenen Link auch alternative Voreinstellungen herunterladen und umbenennen. Angeboten werden im Moment ein vorgefertigter Blog und ein "Blank"-Profil, dass nur die minimalsten Voreinstellungen enthält und für Entwickler interessant ist.

#####Schritt 2: Check der Installationvorraussetzungen

Danach wird die Systemkompatibilität geprüft. Für die meisten Webserver sollte es hier keine Probleme geben. Die hier gezeigten Fehler entstanden aufgrund einer lokalen Installation. Die fehlenden Berechtigungen sind jedoch schnell behoben. Sollten noch andere Fehler angezeigt werden sollte man im Zweifelsfall die Systemadministratoren kontaktieren.

#####Schritt 3: MySQL

Die MySQL Datenbankeinrichtung sollte keine Schwierigkeiten machen. Die richtigen Daten in die Felder eintragen und warten, bis die Voreinstellungen installiert sind.

#####Schritt 4: Administrator Konto einrichten

Den Administrator Account erstellen und man ist so gut wie fertig.

#####Schritt 5 & 6: Abschluss der Installation

Man sollte in dem Masse der grünen und vermeintlich fertigen Balken nicht überlesen, dass aus Sicherheitsgründen noch einige Dateien und Ordner wieder gelöscht werden sollten. Desweiteren wird auf die Konfigurationsdatein hingewiesen, die noch erweiterterte Einstellungen nach der Installation bieten. Leider ist dort festzustellen, dass in der Standartinstallation nicht die optimalsten Sicherheitseinstellungen getroffen sind. Danach kann man sich nach der erfolgreichen Installation auf die neue Seite stürzen.

###Erstellung einer Beispielseite