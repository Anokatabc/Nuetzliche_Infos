###### -- Lokales Repository finden (mit cd und dir herumnavigieren)

$\color{yellow}{git rev-parse --show-toplevel}$



##### -- Lokales Repository relokalisieren (u. a. löschen) -> erst hineinnavigieren

 	*/s = subdirectories*

 	*/q = ohne Bestätigung*

 	*.git = \[Dateiordner]*

$\color{yellow}{**rmdir /s /q .git**}$



##### -- Lokales Repository erstellen (initialisieren) -> erst hineinnavigieren

$\color{yellow}{**git init**}$



##### -- Lokales Repository mit bestehendem R. auf GitHub verbinden.

 	*remote = GitHub, spricht remote repository an.*

 	*add = fügt neue Verbindung zu einem lokalen Repository hinzu*

 	*origin = beliebige Benennung der Verbindung, üblicherweise "origin" für erste/normale Verbindung*

 	*Link = da vom lokalen Repository ausgegangen wird (übers Terminal), muss ein Ziel angegeben sein.*

$\color{yellow}{**git remote add origin REPOSITORYLINK**}$



##### -- Alle Unterordner "stagen" ("ready for commit")

$\color{yellow}{**git add .**}$



##### -- Commit

 	*Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (.git-Ordner)*

 	*-m = Message. Angeben welche Veränderungen es seit dem letzten Commit gegeben hat.*

$\color{yellow}{**git commit -m "Stand Commit: Projekt erstellt"**}$



##### -- (einmalig beim ersten Push) aktuellen Branch in "main" umbenennen.

 	*-M erzwingt die Änderung.*

$\color{yellow}{**git branch -M main**}$



##### -- Pushen

	*-u = setzt upstream-Verbindung (von lokal auf remote).*

	*"origin" = Verbindung zu remote*

	*"main" = aktiver Branch*

	*-f oder --force wenn man überschreiben möchte*

	*-Bei späteren Commits geht einfach nur "git push"*

$\color{yellow}{**git push -u origin main**}$



##### -- Änderungen seit letztem Commit prüfen

$\color{yellow}{**git diff**}$



##### -- Sehen was aktuell gestaged ist

$\color{yellow}{**git status**}$



##### -- Von .git Ordner wiederherstellen (Stand: Letzter Commit)

$\color{yellow}{**git restore .**}$

