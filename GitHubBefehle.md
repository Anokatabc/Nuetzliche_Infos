## GitHub-Befehle (Übersicht)

### Navigation und Erstellung/Einrichtung

#### -- Lokales Repository finden (wenn vorhanden) -> mit `cd` und `dir` herumnavigieren --
```bash
git rev-parse --show-toplevel
```
> Ermittelt von einem Kindelement aus (aufwärts) den Ordner, der als Repository markiert ist.<br>
> Das ist der Ordner, in welchem ".git" liegt. Der ist im normalen Explorer standardmäßig versteckt.

#### -- Lokales Repository erstellen (initialisieren) -> erst in Wunschverzeichnis hineinnavigieren --
```bash
git init
```
> Initialisiert (erstellt) ein lokales Repository im aktuellen Verzeichnis. Alternativ lässt sich auch ein bestimmtes Verzeichnis hinter `init` angeben.

#### -- Lokales Repository mit bestehendem Repository auf GitHub verbinden (nicht nötig nach `clone`) --
```bash
git remote add origin REPOSITORYLINK
```
> `remote` = (hier) GitHub, spricht remote Repository an.

> `add` = Fügt neue Verbindung zu einem lokalen Repository hinzu.

> `origin` = Beliebige Benennung der Verbindung, üblicherweise "origin" für erste/normale Verbindung.

> Ziel-Link = Da anfänglich nur vom lokalen Repository ausgegangen wird, muss ein Ziel angegeben werden.

### Hochladen und Synchronisieren (add (=Stage) -> commit -> push)

### Einmalig bei dem ersten Push
#### -- Aktuellen Branch in "main" umbenennen. 
```bash
git branch -M main
```
> `-M` (Move) erzwingt die Änderung, auch wenn Branch "main" schon existiert.
#### -- Verbindung zum Remote herstellen 
```bash
git push -u origin main
```
> `-u` = setzt Upstream-Verbindung (von local auf remote) - dies bleibt von hier an die Default-Verbindung bei Push&Pull

> `origin` = (beliebiger, aber gängiger Name für) Verbindung zu remote

> `main` = Name des aktiven Branches

> `f` oder `--force` wenn man überschreiben möchte

> -> Bei späteren Commits geht einfach nur `git push`

### Üblicher Upload-Workflow
#### -- Alle Unterordner "stagen" ("ready for commit") --
```bash
git add .
```
> Punkt `.` ist Wildcard für alle Unterordner. Alternativ lassen sich auch spezifische Ordnerpfade angeben.

#### -- Commit --
```bash
git commit -m "Stand Commit: Projekt erstellt"
```
> Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (d. h. im .git-Ordner)

> `-m` = message. Angeben welche Veränderungen es seit dem letzten Commit gegeben hat.

#### -- Pushen --
```bash
git push
```
> Ein Push lädt den Commit auf Remote bzw. GitHub hoch

### Repository von Remote (GitHub) auf Local (PC) Herunterladen

#### -- (Wenn nicht lokal vorhanden) Repository von GitHub herunterladen und lokal erstellen -> ins Wunschverzeichnis hineinnavigieren
```bash
git clone REPOSITORYLINK
```
> `clone` erstellt ein lokales Repository nach dem Vorbild des Remote

#### -- (Wenn lokal vorhanden) Repository von GitHub mit lokalem Repository synchronisieren (downstream)
> Sofern noch kein Initial Commit stattgefunden hat, 

#### -- 
#### -- 

### Verwaltungsbefehle

#### -- Änderungen seit letztem Commit prüfen --
```bash
git diff
```
> Listet im Terminal alle Änderungen auf, die seit letztem Commit stattgefunden haben.

#### -- Sehen was aktuell gestaged ist --
```bash
git status
```
> Listet aktuelle Inhalte im Stage auf.

#### -- Von .git Ordner wiederherstellen (Stand: Letzter Commit) --
```bash
git restore .
```
> Stellt Ordnerstruktur aus dem gespeicherten Repository in .git wiederher. Dazu muss kein lokales Repository bestehen - es wird nur der Ordner benötigt.

#### -- Lokales Repository (unter Windows) löschen -> erst hineinnavigieren --
```bash
rmdir /s /q .git
```
> s = subdirectories

> q = ohne Bestätigung

> git = \[Dateiordner]







