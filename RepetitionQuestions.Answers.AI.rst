=======================================
AI FS13 Repetitionsfragen Antworten
=======================================

Dieses Dokument wird vorzu erweitert. Ergänzungen und Antworten sind herzlich willkommen.
Repetitionsfragen: https://github.com/moonline/AI/blob/master/RepetitionQuestions.AI.tex


Analytische Optimierungsprobleme
================================
1) 
	Regeln
		* Der Barbier schneidet allen die Haare, die sich selbst nicht die Haare schneiden
	Problem
		Wenn sich der Barbier selbst nicht die Haare schneidet, müsste er sich selbst die Haare schneiden, womit er sich selbst die Haare schneidet und sich selbst die Haare nicht schneiden sollte
	Lösung
		Das Problem ist ein sogenannt aniomisches Problem und nicht lösbar.
		
		
Einführung in die Künstliche Intelligenz
========================================
2)
	* Sprach-/Bilderkennung
	* Erzeugung von neuem Wissen aus bestehendem
	* Automatisches Programmieren
	* Expertensysteme
	
3)
	* Informationen / Modellen
	* Algorithmen zur Veränderung von Informationen/Modellen
	
4) Weil das Modell nur eine Abstraktion der Realität ist und damit einen bestimmten Fehler beinhaltet.

5) Gödel beschreibt, das ein der Versuch, aus einem System heraus das System komplett zu beschreiben unlösbare Wiedersprüche entstehen. z.B. Kann ein Computer nicht alle Probleme lösen oder das menschliche Gehirn wird nie in der Lage sein, seine eigene Funktion vollständig Wiederspruchsfrei zu beschreiben.

6) 
	Situation
		Das Dodon's Problem beschreibt ein Gefängnis mit 100 offenen Zellen in denen Häftlinge sitzen. Zuerst wird jedes, dann jedes zweite, dann jedes 3, ... bis 100. Schloss invertiert (geschlossen wenn offen, geöffnet wenn geschlossen). Die Häftlinge der Türen, die am schluss offens sind, dürfen in die Freiheit.
	Problem
		Welche Türen sind am Schluss offen? / Welches sind die Gewinnerpositionen
	Lösungsansatz mit Mathematica/java
		bool array mit 100 Einträgen
		Mit einer doppelten Schleife über die Einträge iterieren, mit einem inkrementierenden Counter die Sprünge umsetzen
	Lösung
		Quadratzahlen sind Gewinnerpositionen

7) 
	Situation
		Auf einem Schachbrett mit einer Figur/zwei Spielern wird horizontal oder vertikal nach unten oder links gezogen. Gestartet wird in der rechten oberen Ecke.
	Problem
		Wer nicht mehr ziehen Kann hat verloren. Welches sind die Gewinnerpositionen?
	Lösungsansatz mit Sprague Grundi
		Für jedes Feld die Sprague Grundi werte ausrechenen(von 0 aufwärts den kleinsten Wert, der nicht auf einem Feld steht, auf das in diesem Zug direkt gezogen werden kann), die 0-Felder sind Gewinnerpositionen
	Lösungsansatz mit Mathematica/Java
		zweidimensionales int array für das feld
		entweder das spiel tausende male mit Zufallszügen simulieren (spielen) oder
		vom Zielpunkt her für jedes Feld die Sprague Grundi Werte ausrechen
	Lösung
		Die Gewinnerpositionen befinden sich auf der Diagonalen
		
8) Funktion siehe 7, Schleifen: Bei Schleifen kann die Bewertung nicht berechnet werden, weil sie sich selbst unendlich hochschaukeln würde


Matrixen
========
9) eine Matrix mit gleich vielen Spalten und Zeilen

10) 
	* Eine Matrix, zu der es eine inverse gibt (wenn es eine zweite Matrix I gibt, mit deren multipliziert sich die Einheitsmatrix E ergibt -> M x I = E ). 
	* Man kann dies auch überprüfen, indem man die Matrix als Graph schreibt. Is dieser Verbunden, ist die Matrix regulär. 

11) eine Nachbarschaftsmatrix, die einen Graph abbildet. Adjazenzmatrixen sind immer quadratisch.

12) 
	stochiastische Matrix
		eine Matrix, deren Zeilen- und Spaltensummen 1 betragen
	Zeilenstochiastische Matrix
		wenn alle Einträge der Matrix zwischen 0 und 1 liegen und die Zeilensummen 1 ergeben.
	Spaltenstochiastische Matrix
		wenn alle Einträge der Matrix zwischen 0 und 1 liegen und die Spaltensummen 1 ergeben.
	rechtsstochiastische Matrix
		?
	linksstochiastische Matrix
		?
		
13) Mit einer Adjazenzmatrix. Die Knoten des Graphen werden nummeriert und den Zeilen und Spalten der Matrix zugeteilt. Eine 1 in einem Matrix Feld definiert eine von-zu Kante.
	Beispiel::
	
		| 0 1 0 |					        .<-----.
		| 1 1 0 |					(3)<---(1)--->(2)--.
		| 1 0 0 |					               ^---'
		Verbindungen bestehen zwischen den Knoten 1 und 2, 2 und 1, 2 mit sich selbst, 3 und 1.
		
		
14) Durch Multiplizierung der Matrix mit sich selbst.


Optimierungen
=============

Eindimensionale Optimierungen
-----------------------------
15)
	a) 
		Vorgenen
			Es wird eine Kurve erstellt mit Dunkelheit/Weg. Durch Gradientenabstieg wird der Ort der kleinsten Dunkelheit (kleinster Fehler) gefunden.
		Skizze::
		
			D.ht.^       ..-+-..
			     |   .-'        '-.
			     | .'              '.
			     |'                  '
			     +--------------------+-> Weg
			     '          a         '
			Kerze A                Kerze B
		
		
		Lösung
			Am Hellsten ist direkt bei der einen oder der andern Kerze
			
	b)
		Skizze::
		
			-----Strasse----------------
			            <-s->          ^     
			                           f
			                        +  v
			                            
			Vs Geschwindigkeit Strasse, Vf Geschwindigkeit auf dem Feld
			
			
		Vorgehen::
		
			sp: Teilstrecke der Strasse, bis zum Abbiegepunkt
			t = sp/Vs+fp/Vf
			fp = sqrt((s-sp)^2+f^2)
			
			Wie oben Diagramm mit Zeit/Weg bis Abbiegepunkt erstellen, mit Gradientenabstieg das Minimum finden
			

16) Eine Funktion mit einem Freiheitsgrad wird durch weitere Bedingungen (Nebenbedingungen) eingeschränkt. Lagrange Multiplikatoren helfen, die Nebenbedingungen über eine weitere Unbekannte in die Gleichung einzubauen, sodass nur noch eine Gleichung zu lösen ist.
	Beispiel::
	
		f(x,y) Gleichung
		g(x,y) = c Nebenbedingungen
		
		A(x,y,l) = f(x,y) + l*(g(x,y)-c)
		l = Lagrangemultiplikator
		
	
	Schiffbeispiel::
	
		      A       C
		------*-------*--------          ------*-------*--------
		       \     /                          \  a  /
		        \   /                            ° - .
		         \ /                              \ /
		----------*------------          ----------*------------
		          B
		Vx Geschwindigkeit Schiff von A nach B
		Vy Geschwindigkeit Schiff von B nach C
		b Winkel bei b
		sx, sy Streckenlänge
		a Abstand der Schiffe
		
		v = s/t s = v*t
		
		svx = Vx*t
		svy = Vy*t
		
		a^2 = (sx-svx)^2 + svy^2 - 2*(sx-svx)*svy*cos(b)
		f(t) = (sx-Vx*t)^2 + (Vy*t)^2 - 2*(sx-Vx*t)*Vy*t*cos(b)
		sx, sy, Vx, Vy und b einsetzen, Minimum auf Kurve bestimmen
		
		
17) Faktoren, mit denen Nebenbedingungen multipliziert werden müssen, damit die Gleichung lösbar wird.


Mehrdimensionale Optimierungen
------------------------------
18) ::
	
		x^2 + 0.25y^2
		
		Jede Gleichung einzeln ableiten
		dx/x x^2 + 0.25y^2 = 2x
		dy/y x^2 + 0.25y^2 = 0.5y
		
		Nullpunkt der einzelnen Gleichungen finden
		2x = 0
		0.5y = 0
		
		Minimum bei 0/0
		
		
19) Ein Gradient wird solange verändert, bis der Fehler der Gleichung am Minimum angelangt ist. Anschliessend wiederholt man dies mit jedem Gradienten. Den Gesammten Vorgang macht man so lange, bis sich der Fehler nicht mehr verändert.

20) Die Nebenbedingungen werden in Gleichungen überführt. Die Haupt und Nebengleichungen werden in die Simplex-Tabelle eingetragen. Anschliessend wird mit Simplex Iterationen der Zielwert angenähert.
	http://www.anginf.de/download/bwl/ibl/simplex.html
	
21) Eine Menge, deren Rand stets eine nach aussen gewölbte oder Flache kante hat (keine Einbuchtung) und damit die Verbindungsstrecken zwischen sämmtlichen Punkten der Menge ebenfalls innerhalb der Figur liegen.



		
		