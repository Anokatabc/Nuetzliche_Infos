## GitHub-Befehle (Übersicht)

##### -- Lokales Repository finden (mit cd und dir herumnavigieren)

#### $\color{yellow}\textbf{git rev-parse --show-toplevel}$



#### -- Lokales Repository relokalisieren (u. a. löschen) -> erst hineinnavigieren

$\small \text \quad	{/s = subdirectories}$

$\small \text \quad	{/q = ohne Bestätigung}$

$\small \text \quad	{.git = \[Dateiordner]}$

#### $\color{yellow}\textbf{rmdir /s /q .git}$



#### -- Lokales Repository erstellen (initialisieren) -> erst hineinnavigieren

#### $\color{yellow}\textbf{git init}$



#### -- Lokales Repository mit bestehendem R. auf GitHub verbinden.

$\small \text \quad	{remote = GitHub, spricht remote repository an.}$

$\small \text \quad	{add = fügt neue Verbindung zu einem lokalen Repository hinzu}$

$\small \text \quad	{origin = beliebige Benennung der Verbindung, üblicherweise "origin" für erste/normale Verbindung}$

$\small \text \quad	{Link = da vom lokalen Repository ausgegangen wird (übers Terminal), muss ein Ziel angegeben sein.}$

#### $\color{yellow}\textbf{git remote add origin REPOSITORYLINK}$



#### -- Alle Unterordner "stagen" ("ready for commit")

#### $\color{yellow}\textbf{git add .}$



#### -- Commit

$\small \text \quad	{Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (.git-Ordner)}$

$\small \text \quad	{-m = Message. Angeben welche Veränderungen es seit dem letzten Commit gegeben hat.}$

#### $\color{yellow}\textbf{git commit -m "Stand Commit: Projekt erstellt"}$



#### -- (einmalig beim ersten Push) aktuellen Branch in "main" umbenennen.

$\small \text \quad	{-M erzwingt die Änderung.}$

#### $\color{yellow}\textbf{git branch -M main}$



#### -- Pushen

	$\small \text {-u = setzt upstream-Verbindung (von lokal auf remote).}$

	$\small \text {"origin" = Verbindung zu remote}$

	$\small \text {"main" = aktiver Branch}$

	$\small \text {-f oder --force wenn man überschreiben möchte}$

	$\small \text {-Bei späteren Commits geht einfach nur "git push"}$

#### $\color{yellow}\textbf{git push -u origin main}$



#### -- Änderungen seit letztem Commit prüfen

#### $\color{yellow}\textbf{git diff}$



#### -- Sehen was aktuell gestaged ist

#### $\color{yellow}\textbf{git status}$



#### -- Von .git Ordner wiederherstellen (Stand: Letzter Commit)

#### $\color{yellow}\textbf{git restore .}$

