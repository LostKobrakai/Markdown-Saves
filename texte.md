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
ProcessWire läuft auf Apache mit aktuellen Versionen von PHP und MySQL. Weitere Datenbanktypen werden dabei nicht unterstützt. Vor allem aufgrund der geringen Nutzerbasis gibt es bisher keine Hoster, die ProcessWire bereits vorinstalliert anbieten.

> Ein Unix oder Windows Webserver mit Apache

> PHP Version 5.2.4 oder neuer

> MySQL 5.0.15 oder neuer

> mod_rewrite muss aktiviert sein

> .htaccess Daten müssen nutzbar sein

> Die GD 2 Bibliothek muss in PHP installiert sein

> PHP muss mysqli unterstützen

> Optional: Multi-byte String Unterstüzung in PHP (mbstring)

> Optional: PHP Kurztags aktiviert

####Start

Die ProcessWire Installation funktioniert über ein Webinterface, das mit dem Softwarepaket mitgeliefert wird. Beim ersten Aufruf des Stammverzeichnis wird man automatisch auf die Installationsseite weitergeleitet.

####Schritt 1: Seitenvoreinstellungen wählen

Vor der Installation wird man dazu aufgefordert den Ordner der vorinstallierten Webseite umzubenennen. Alternativ könnte man sich unter dem angegebenen Link auch alternative Voreinstellungen herunterladen und umbenennen. Angeboten werden im Moment ein vorgefertigter Blog und ein "Blank"-Profil, dass nur die minimalsten Voreinstellungen enthält und für Entwickler interessant ist.

####Schritt 2: Check der Installationvorraussetzungen

Danach wird die Systemkompatibilität geprüft. Für die meisten Webserver sollte es hier keine Probleme geben. Die hier gezeigten Fehler entstanden aufgrund einer lokalen Installation. Die fehlenden Berechtigungen sind jedoch schnell behoben. Sollten noch andere Fehler angezeigt werden sollte man im Zweifelsfall die Systemadministratoren kontaktieren.

####Schritt 3: MySQL

Die MySQL Datenbankeinrichtung sollte keine Schwierigkeiten machen. Die richtigen Daten in die Felder eintragen und warten, bis die Voreinstellungen installiert sind.

####Schritt 4: Administrator Konto einrichten

Den Administrator Account erstellen und man ist so gut wie fertig.

####Schritt 5 & 6: Abschluss der Installation

Man sollte in dem Masse der grünen und vermeintlich fertigen Balken nicht überlesen, dass aus Sicherheitsgründen noch einige Dateien und Ordner wieder gelöscht werden sollten. Desweiteren wird auf die Konfigurationsdatein hingewiesen, die noch erweiterterte Einstellungen nach der Installation bieten. Leider ist dort festzustellen, dass in der Standartinstallation nicht die optimalsten Sicherheitseinstellungen getroffen sind. Danach kann man sich nach der erfolgreichen Installation auf die neue Seite stürzen.

###Erstellung einer Beispielseite

####Idee

Die Präsentation von ProcessWire direkt auf dem System aufgebaut zeigt am besten wie einfach das System zu nutzen ist. Außerdem zeigt es viel besser, was mit den Einstellung im Backend letztlich erreicht wurde.

####Struktur

Der Inhalt der Webseite sollte nun auf verschiedene Einzelseiten aufgeteilt werden. Das erleichtert die spätere Bearbeitbarkeit der Texte im Backend. Dabei kann ich auf die bestehende Überschriftenstruktur meiner Texte zurückgreifen.

	#Processwire
	##Was ist Processwire
	##Warum habe ich mich für Processwire entschieden
	###Pages
	####Hierarchie
	####Alles ist gleich
	####Custom Fields
	###API
	###Sonstige Eigenschaften
	####Theming
	####Module
	####Rechtemanagement
	####Community
	##Praktische Anwendung
	###Installation
	####Vorraussetzungen
	####Start
	####Schritt 1: Seitenvoreinstellungen wählen
	####Schritt 2: Check der Installationvorraussetzungen
	####Schritt 3: MySQL
	####Schritt 4: Administrator Konto einrichten
	####Schritt 5 & 6: Abschluss der Installation
	###Erstellung einer Beispielseite
	####Idee
	####Struktur

####Aufbau im Backend

Bevor ich angefangen habe die Seiten zu erstellen, habe ich alle unnützen Seiten, Templates und Felder gelöscht, um jetzt sauber meine eigenen Seiten zu erstellen. Da ich meine Seitenstruktur im Backend nach meinen Überschriften richte fällt es nicht schwer ein Template dafür zu erstellen. Jede Überschrift hat einen Titel und optional Text dazu. Unterpunkte erstelle ich durch die Hierarchie im Seitenbaum.

Unter Add Template erstelle ich ein neues Template `heading-structure`. Ich erstelle erstmal das Backend und füge danach die Templatedatei hinzu. Alternativ könnte man hier auch ein Template zu einer bereits bestehenden Templatedatei erstellen. Hier wäre das für das Impressum möglich.

Danach bearbeite ich das neu erstellte Template. Als Felder ist bereits title enthalten. Dieses ist für alle Seiten nötig. Ich füge nun meine eigenen Felder an: `heading`, `images` und `body`, also Headline und Text.

In den anderen Tabs könnte man jetzt noch genauere Einstellungen zu dem Template treffen, diese sind bis auf eine Ausnahme nicht nötig.

Da meine Webseite am Ende aus einer Seite bestehen soll, werden die Inhalte aus allen `heading-structure` Seiten zusammengefügt, um dabei die Kontrolle über die Inhalte zu behalten und dass nicht zufällig eine falsche Seite in mein Dokument gelangt verbiete ich andere Templates außer `heading-structure` als Kindseiten einer `heading-structure` Seite. Dies ist möglich unter `FAMILY`, `Allowed tamplate(s) for children`.

Nun erstelle ich die erste Seite. Headline und Text einfügen und speichern sowie veröffentlichen. Das mache ich mit allen Unterüberschriften und deren Texten und Bildern. Bilder lassen sich im Body einfügen, da dieser kein reines Textfeld, sondern ein Rich-Text-Editor beinhaltet. Organisiert werden die Bilder jedoch über das Images-Feld. Am Ende habe ich dann im Seitenbaum einen Ast mit meine ganze Textstruktur.

####Templatedatei erstellen

Bisher ist der komplette Text nur in einzelnen Teilen im Backend zu sehen. Nun erstelle ich eine neue Templatedatei `heading-structure.php`, über die dann letztlich die Seite ausgegeben wird. Sobald die Datei im Ordner `/site/templates` ist, wird sie automatisch erkannt und mit dem Template im Backend verwendet.

	<?php
	/**
	 * Documents template
	 *
	 */

	//Daten holen - Nur ein Aufruf für mehrere Anwendungen
	function fetch_data($page, $depth=1){
		$heading[0] = array($page->id, $page->get("headline|title"), $page->body, $depth);

		if(count($page->children) > 0){
			foreach($page->children as $child){
				$children[] = fetch_data($child, $depth+1);
			}
			$heading[1] = $children;
		}
		return $heading;
	}
	//Funktionsaufruf
	$data = fetch_data($page);

	//HTML für die Webseite an sich
	function recurse_html($data){
		$id = $data[0][0];
		$title = $data[0][1];
		$body = $data[0][2];
		$depth = $data[0][3];

		//HTML Ausgeben
		echo "<h$depth class='h_".$id."' id='$id' name='$id'>".$title."</h$depth>\n";
		if($body) echo $body."\n";
		if(isset($data[1])){
			foreach($data[1] as $child){
				recurse_html($child);
			}
		}
	}

	//HTML für die Navigation
	function recurse_list($data, $maxdepth=0){
		$id = $data[0][0];
		$title = $data[0][1];
		$depth = $data[0][3];

		//HTML Liste Ausgeben
		echo "<li class=''><a href='#$id' class='h_$id d_$depth'>".$title."</a></li>\n";
		if(isset($data[1]) && $depth < $maxdepth){
			foreach($data[1] as $child){
				recurse_list($child, $maxdepth);
			}
		}
	}

	?>
	<!doctype html>
	<html lang="de">
	<head>
		<meta charset="UTF-8">
		<title><?php echo $page->get("headline|title"); ?> &mdash; Benjamin Milde</title>
		<link href='http://fonts.googleapis.com/css?family=Merriweather:400,900' rel='stylesheet' type='text/css'>
		<link rel="stylesheet" type="text/css" href="<?php echo $config->urls->templates?>style.css">
		<script type="text/javascript" src="<?php echo $config->urls->templates?>scripts/jquery-1.4.2.min.js"></script>
		<script type="text/javascript" src="<?php echo $config->urls->templates?>scripts/rainbow-custom.min.js"></script>
		<link rel="stylesheet" type="text/css" href="<?php echo $config->urls->templates?>scripts/rb/github.css">
		<script type="text/javascript">
		$(document).ready(function(){
			$('nav').bind({click: function(){
				$('ul', this).toggleClass("hovered");
			}, mouseenter: function(){
				$('ul', this).addClass("hovered");
			}, mouseleave: function(){
				$('ul', this).removeClass("hovered");
			}});
			$("code").each(function(){
				if($(this).attr("data-language") == undefined){
					$(this).attr("data-language", "php");
				}
			});
		});
		</script>
	</head>
	<body>
		<nav>
			<ul>
				<?php recurse_list($data, 3); ?>
			</ul>
		</nav>
		<?php recurse_html($data); ?>
	</body>
	</html>

Die Templatedatei sieht ersteinmal sehr kompliziert aus. Dabei ist es garnicht so schwierig. Die Datei besteht aus 2 logischen Teilen. Der obere Teil mit den 3 Funktionen sorgt für die Datenabwicklung, während in der zweiten Hälfte das HTML Template steht, in das nurnoch mit kurzen Funktionsaufrufen (`<?php recurse_list($data, 3); ?>`, `<?php recurse_html($data); ?>`) die Daten eingebettet werden.

Zu der ersten Hälfte ist nicht viel zu sagen, außer, dass man genau sieht, dass die Daten mit annähernd keinem Markup übergeben werden. Lediglich `$page->body` liefert einige HTML-Tags zum Beispiel für Absätze, `<p>`, oder für Zitate, `<blockquote>`. Die komplette Verarbeitung der Daten muss man selbstständig aufbauen. Was aufwendig klingt hat jedoch die Vorteile, dass man nicht erst viele systemeigene Funktionen lernen muss bevor man anfangen kann und die volle Kontrolle über den Prozess behält. In meinem Fall verhindere ich bewusst einen 2ten großen Datenbankaufruf, indem ich die Daten lokal zwischenspeichere, um sie dann dafür 2 mal, für die Navigation und den Seiteninhalt, zu verarbeiten.

Das HTML Template ist auf Grund der simplen Seitenstruktur relativ klein. Für mehrseitige Templates könnte man Kopf- und Fußbereiche der Seite auch in externe Dateien, z.B. `head.inc` und `footer.inc`, auslagern. Damit lassen sie sich in anderen Templates wiederverwenden. Da ich nur ein Template nutze, spare ich die Aufrufe zusätzlicher Dateien.

##Fazit

Ich bin froh mit ProcessWire ein Content-Management-System gefunden zu haben, dass mich als Webentwickler mehr unterstützt, als mich zu behindern. Meine Erfahrungen mit anderen Systemen wie Wordpress, Joomla oder Drupal haben gezeigt, dass es oft ein langwieriges Lesen der Dokumentation bedarf bis man eine Seite nach seinen Wünschen aufgebaut hat. ProcessWire dagegen lässt den Entwickler mit bereits bekanntem  arbeiten und liefert nur eine API für den Datentransfer.