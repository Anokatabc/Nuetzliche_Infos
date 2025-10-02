## GitHub-Befehle (Übersicht)

#### -- Lokales Repository finden (mit cd und dir herumnavigieren)

### $\color{yellow}\textbf{git rev-parse --show-toplevel}$



### -- Lokales Repository relokalisieren (u. a. löschen) -> erst hineinnavigieren

$\small \qquad \text	{/s = subdirectories}$

$\small \qquad \text	{/q = ohne Bestätigung}$

$\small \qquad \text	{.git = \[Dateiordner]}$

### $\color{yellow}\textbf{rmdir /s /q .git}$



### -- Lokales Repository erstellen (initialisieren) -> erst hineinnavigieren

### $\color{yellow}\textbf{git init}$



### -- Lokales Repository mit bestehendem R. auf GitHub verbinden.

$\small \qquad \text	{remote = GitHub, spricht remote repository an.}$

$\small \qquad \text	{add = fügt neue Verbindung zu einem lokalen Repository hinzu}$

$\small \qquad \text	{origin = beliebige Benennung der Verbindung, üblicherweise "origin" für erste/normale Verbindung}$

$\small \qquad \text	{Link = da vom lokalen Repository ausgegangen wird (übers Terminal), muss ein Ziel angegeben sein.}$

### $\color{yellow}\textbf{git remote add origin REPOSITORYLINK}$



### -- Alle Unterordner "stagen" ("ready for commit")

### $\color{yellow}\textbf{git add .}$



### -- Commit

$\small \qquad \text	{Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (.git-Ordner)}$

$\small \qquad \text	{-m = Message. Angeben welche Veränderungen es seit dem letzten Commit gegeben hat.}$

### $\color{yellow}\textbf{git commit -m "Stand Commit: Projekt erstellt"}$



### -- (einmalig beim ersten Push) aktuellen Branch in "main" umbenennen.

$\small \qquad \text	{-M erzwingt die Änderung.}$

### $\color{yellow}\textbf{git branch -M main}$



### -- Pushen

$\small \qquad \text {-u = setzt upstream-Verbindung (von lokal auf remote).}$

$\small \qquad \text {"origin" = Verbindung zu remote}$

$\small \qquad \text {"main" = aktiver Branch}$
 
$\small \qquad \text {-f oder --force wenn man überschreiben möchte}$

$\small \qquad \text {-Bei späteren Commits geht einfach nur "git push"}$

### $\color{yellow}\textbf{git push -u origin main}$



### -- Änderungen seit letztem Commit prüfen

### $\color{yellow}\textbf{git diff}$



### -- Sehen was aktuell gestaged ist

### $\color{yellow}\textbf{git status}$



### -- Von .git Ordner wiederherstellen (Stand: Letzter Commit)

### $\color{yellow}\textbf{git restore .}$

