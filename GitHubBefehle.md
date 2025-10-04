## $${\text{\color{blue}GitHub-Befehle (Übersicht)}}$$

### $${\text{\color{blue} A. Üblicher Upload-Workflow | 1) add (=Stage) -> 2) commit -> 3) push}}$$
#### -- 1) __Add__ - Alle Unterordner "stagen" ("ready for commit") --
```bash
git add .
```
> Punkt `.` ist Wildcard für alle Unterordner. Alternativ lassen sich auch spezifische Ordnerpfade angeben.

#### -- 2) __Commit__ (in ".git" / im lokalen Repository speichern)--
```bash
git commit -m "Stand Commit: Projekt erstellt"
```
> Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (d. h. im .git-Ordner).

> `-m` = message. Angeben welche Veränderungen es seit dem letzten Commit gegeben hat.

#### -- 3) __Push__ (lokales Repository auf das remote Repository hochladen) --
```bash
git push
```
> Ein Push lädt den Commit auf remote bzw. GitHub hoch.<br>
> Sofern es der erste Push überhaupt ist, am besten einmal Abschnitt C anschauen.

#### -- Neuen Branch erstellen
```bash
git checkout -b BRANCHNAME
```
> `-b` steht für Branch.
> Erstellt und wechselt zu einem neuen Branch mit dem angegebenen Namen. Alle seit dem letzten Commit vorgenommenen Änderungen werden auf diesen neuen Branch überschrieben. Der alte Branch verbleibt auf dem Stand des Commits.
#### -- Aktiven Branch wechseln
```bash
git checkout BRANCHNAME
```
> Findet in der Regel nur in größeren Projekten Anwendung, um zwischen verschiedenen Bearbeitungsversionen oder Aufgabenbereichen zu wechseln.
> In modernen Projekten wird häufig auch `git switch [BRANCHNAME]` verwendet.

#### -- Datei öffnen bzw. geöffnete Datei auf Commit-Stand zurücksetzen
```bash
git checkout DATEINAME
```
> z.B. `git checkout README.md`
> Öffnet die angegebene Datei im remote Repository. Sollte diese Datei aktuell geöffnet sein, wird der Arbeitsbereich auf den Stand des letzten Commits zurückgesetzt.

#### -- (Später) fetch, log und merge in Teamarbeit
...

### $${\text{\color{blue} B. Navigation und Erstellung/Einrichtung}}$$

#### -- Lokales Repository finden (wenn vorhanden) -> mit `cd` und `dir` herumnavigieren --
```bash
git rev-parse --show-toplevel
```
> Ermittelt von einem Kindelement aus (aufwärts) den Ordner, der als Repository markiert ist.<br>
> Das ist der Ordner, in welchem ".git" liegt. Der ist im normalen Datei-Explorer standardmäßig versteckt.

#### -- Lokales Repository erstellen (initialisieren) -> erst in Wunschverzeichnis hineinnavigieren --
```bash
git init
```
> Initialisiert (erstellt) ein lokales Repository im aktuellen Verzeichnis. Alternativ lässt sich auch ein bestimmtes Verzeichnis hinter `init` angeben, z.B. `git init C:\Users\Projekte\NeuesRepository`

#### -- Lokales Repository mit bestehendem Repository auf GitHub verbinden (nicht nötig nach `clone`) --
```bash
git remote add origin REPOSITORYLINK
```
> `remote` = (hier) GitHub, spricht remote Repository an. Z.B. `git remote add origin github.com/user/repository123`

> `add` = Fügt neue Verbindung zu einem lokalen Repository hinzu.

> `origin` = "origin" ist eine gängige Benennung für die Verbindung zum remote Repository.

> Ziel-Link = Da anfänglich nur vom lokalen Repository ausgegangen wird, muss ein Ziel angegeben werden.

### $${\text{\color{blue} C. Einmalig bei dem ersten Push}}$$
#### -- Aktuellen Branch in "main" umbenennen. 
```bash
git branch -M main
```
> `-M` (Move) erzwingt die Änderung, auch wenn Branch "main" schon existiert.
#### -- Verbindung zum remote herstellen 
```bash
git push -u origin main
```
> `-u` = setzt Upstream-Verbindung (von local auf remote) - dies bleibt von hier an die Default-Verbindung bei Push&Pull.

> `origin` = (beliebiger, aber gängiger Name für) Verbindung zu remote.

> `main` = Name des aktiven Branches.

> `-f` oder `--force` wenn man überschreiben möchte - dies könnte u. U. nötig sein falls Default-Einstellungen etwas blockieren.

> -> Bei späteren Commits geht einfach nur `git push`

### $${\text{\color{blue} D. Repository von remote (GitHub) auf local (PC) Herunterladen}}$$

#### -- (Wenn nicht lokal vorhanden) Repository von GitHub herunterladen und lokal erstellen -> vorher ins Wunschverzeichnis hineinnavigieren
```bash
git clone REPOSITORYLINK
```
> `clone` erstellt ein lokales Repository nach dem Vorbild des remote, z.B. `git clone github.com/user/repository123`
> Es wird im aktuell geöffneten Ordner ein neuer Ordner mit dem Repository-Namen erstellt.
> Alternativ kann ein Zielordner angegeben werden, der zum Repository gemacht werden soll, z.B. `git clone REPOSITORYLINK NeuesRepository` (alternativ absoluter Pfad C:\...).

### $${\text{\color{blue} E. Verwaltungsbefehle}}$$

#### -- Änderungen seit letztem Commit prüfen --
```bash
git diff
```
> Listet im Terminal alle Änderungen auf, die seit dem letzten Commit stattgefunden haben.

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














