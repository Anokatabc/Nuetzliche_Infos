###### -- Lokales Repository finden (mit cd und dir herumnavigieren)

**git rev-parse --show-toplevel**



##### -- Lokales Repository relokalisieren (u. a. löschen) -> erst hineinnavigieren

 	$\color{yellow}{"*/s = subdirectories*"}$

 	$\color{yellow}{*"/q = ohne Bestätigung"*}$

 	$\textcolor{yellow}{*.git = \[Dateiordner]*}$

**rmdir /s /q .git**



##### -- Lokales Repository erstellen (initialisieren) -> erst hineinnavigieren

**git init**



##### -- Lokales Repository mit bestehendem R. auf GitHub verbinden.

 	$\color{yellow}{*remote = GitHub, spricht remote repository an.*}$

 	$\color{yellow}{*add = fügt neue Verbindung zu einem lokalen Repository hinzu*}$

 	$\color{yellow}{*origin = beliebige Benennung der Verbindung, üblicherweise "origin" für erste/normale Verbindung*}$

 	$\color{yellow}{*Link = da vom lokalen Repository ausgegangen wird (übers Terminal), muss ein Ziel angegeben sein.*}$

**git remote add origin REPOSITORYLINK**



##### -- Alle Unterordner "stagen" ("ready for commit")

**git add .**



##### -- Commit

 	$\color{yellow}{*Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (.git-Ordner)*}$

 	$\color{yellow}{*-m = Message. Angeben welche Veränderungen es seit dem letzten Commit gegeben hat.*}$

**git commit -m "Stand Commit: Projekt erstellt"**



##### -- (einmalig beim ersten Push) aktuellen Branch in "main" umbenennen.

 	$\color{yellow}{*-M erzwingt die Änderung.*}$

**git branch -M main**



##### -- Pushen

	$\color{yellow}{*-u = setzt upstream-Verbindung (von lokal auf remote).*}$

	$\color{yellow}{*"origin" = Verbindung zu remote*}$

	$\color{yellow}{*"main" = aktiver Branch*}$

	$\color{yellow}{*-f oder --force wenn man überschreiben möchte*}$

	$\color{yellow}{*-Bei späteren Commits geht einfach nur "git push"*}$

**git push -u origin main**



##### -- Änderungen seit letztem Commit prüfen

**git diff**



##### -- Sehen was aktuell gestaged ist

**git status**



##### -- Von .git Ordner wiederherstellen (Stand: Letzter Commit)

**git restore .**

