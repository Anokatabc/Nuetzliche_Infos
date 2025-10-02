## GitHub-Befehle (Übersicht)

##### -- Lokales Repository finden (mit cd und dir herumnavigieren)

<large>$\color{yellow}\textbf{git rev-parse --show-toplevel}$</large>



#### -- Lokales Repository relokalisieren (u. a. löschen) -> erst hineinnavigieren

$\small \text	{/s = subdirectories}$

$\small \text	{/q = ohne Bestätigung}$

$\small \text	{.git = \[Dateiordner]}$

<large>$\color{yellow}\textbf{rmdir /s /q .git}$</large>



#### -- Lokales Repository erstellen (initialisieren) -> erst hineinnavigieren

<large>$\color{yellow}\textbf{git init}$</large>



#### -- Lokales Repository mit bestehendem R. auf GitHub verbinden.

$\small \text	{remote = GitHub, spricht remote repository an.}$

$\small \text	{add = fügt neue Verbindung zu einem lokalen Repository hinzu}$

$\small \text	{origin = beliebige Benennung der Verbindung, üblicherweise "origin" für erste/normale Verbindung}$

$\small \text	{Link = da vom lokalen Repository ausgegangen wird (übers Terminal), muss ein Ziel angegeben sein.}$

<large>$\color{yellow}\textbf{git remote add origin REPOSITORYLINK}$</large>



#### -- Alle Unterordner "stagen" ("ready for commit")

<large>$\color{yellow}\textbf{git add .}$</large>



#### -- Commit

$\small \text	{Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (.git-Ordner)}$

$\small \text	{-m = Message. Angeben welche Veränderungen es seit dem letzten Commit gegeben hat.}$

<large>$\color{yellow}\textbf{git commit -m "Stand Commit: Projekt erstellt"}$</large>



#### -- (einmalig beim ersten Push) aktuellen Branch in "main" umbenennen.

$\small \text	{-M erzwingt die Änderung.}$

<large>$\color{yellow}\textbf{git branch -M main}$</large>



#### -- Pushen

	$\small \text {-u = setzt upstream-Verbindung (von lokal auf remote).}$

	$\small \text {"origin" = Verbindung zu remote}$

	$\small \text {"main" = aktiver Branch}$

	$\small \text {-f oder --force wenn man überschreiben möchte}$

	$\small \text {-Bei späteren Commits geht einfach nur "git push"}$

<large>$\color{yellow}\textbf{git push -u origin main}$</large>



#### -- Änderungen seit letztem Commit prüfen

<large>$\color{yellow}\textbf{git diff}$</large>



#### -- Sehen was aktuell gestaged ist

<large>$\color{yellow}\textbf{git status}$</large>



#### -- Von .git Ordner wiederherstellen (Stand: Letzter Commit)

<large>$\color{yellow}\textbf{git restore .}$</large>

