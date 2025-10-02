## GitHub-Befehle (Übersicht)

### Navigation und Erstellung/Einrichtung

##### -- Lokales Repository finden (mit cd und dir herumnavigieren) --

```bash
git rev-parse --show-toplevel
```



#### -- Lokales Repository erstellen (initialisieren) -> erst in Wunschverzeichnis hineinnavigieren --

```bash
git init
```


#### -- Lokales Repository mit bestehendem Repository auf GitHub verbinden. --

$\small \qquad \text	{remote = GitHub, spricht remote repository an.}$

$\small \qquad \text	{add = fügt neue Verbindung zu einem lokalen Repository hinzu}$

$\small \qquad \text	{origin = beliebige Benennung der Verbindung, üblicherweise "origin" für erste/normale Verbindung}$

$\small \qquad \text	{Link = da vom lokalen Repository ausgegangen wird (übers Terminal), muss ein Ziel angegeben sein.}$

```bash
git remote add origin REPOSITORYLINK
```


### Hochladen und Synchronisieren (add (=Stage) -> commit -> push)

#### -- (einmalig vor dem ersten Push) aktuellen Branch in "main" umbenennen. --

$\small \qquad \text	{-M (Move) erzwingt die Änderung, auch wenn Branch "main" schon existiert.}$

```bash
git branch -M main
```

$\small \qquad \text {-u = setzt Upstream-Verbindung (von lokal auf remote) - dies bleibt von hier an die Default-Verbindung bei Push&Pull}$

$\small \qquad \text {"origin" = (beliebiger, aber gängiger Name für) Verbindung zu remote}$

$\small \qquad \text {"main" = Name des aktiven Branches}$
 
$\small \qquad \text {`-f` oder `--force` wenn man überschreiben möchte}$

$\small \qquad \text {-Bei späteren Commits geht einfach nur "git push"}$

```bash
git push -u origin main
```

#### -- Alle Unterordner "stagen" ("ready for commit") --

```bash
git add .
```


#### -- Commit --

$\small \qquad \text	{Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (.git-Ordner)}$

$\small \qquad \text	{-m = Message. Angeben welche Veränderungen es seit dem letzten Commit gegeben hat.}$

```bash
git commit -m "Stand Commit: Projekt erstellt"
```

#### -- Pushen --





### Repository von Remote (GitHub) auf Local (PC) Herunterladen

#### -- (Wenn nicht lokal vorhanden) Repository von GitHub herunterladen und lokal erstellen -> ins Wunschverzeichnis hineinnavigieren
$\small \qquad \text {clone erstellt ein lokales Repository nach dem Vorbild des Remote}$
```bash
git clone REPOSITORYLINK
```
#### -- (Wenn lokal vorhanden) Repository von GitHub mit lokalem Repository synchronisieren (downstream)
$\small \qquad \text {Sofern noch kein}$

#### -- 
#### -- 

### Verwaltungsbefehle

#### -- Änderungen seit letztem Commit prüfen --

```bash
git diff
```


#### -- Sehen was aktuell gestaged ist --

```bash
git status
```


#### -- Von .git Ordner wiederherstellen (Stand: Letzter Commit) --

```bash
git restore .
```

#### -- Lokales Repository (unter Windows) löschen -> erst hineinnavigieren --

$\small \qquad \text	{/s = subdirectories}$

$\small \qquad \text	{/q = ohne Bestätigung}$

$\small \qquad \text	{.git = \[Dateiordner]}$

```bash
rmdir /s /q .git
```









