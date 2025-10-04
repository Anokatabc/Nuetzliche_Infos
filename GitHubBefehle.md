## $${\text{\color{blue}GitHub-Befehle (Übersicht)}}$$

### $${\text{\color{blue}Üblicher Upload-Workflow | 1) add (=Stage) -> 2) commit -> 3) push}}$$
#### -- 1) __Add__ - Alle Unterordner "stagen" ("ready for commit") --
```bash
git add .
```
> Punkt `.` ist Wildcard für alle Unterordner. Alternativ lassen sich auch spezifische Ordnerpfade angeben, z.B. `git add index.html`

#### -- 2) __Commit__ (in ".git" / im lokalen Repository speichern)--
```bash
git commit -m "Stand Commit: Projekt erstellt"
```
> Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (d. h. im .git-Ordner).

> `-m` = message. Angeben welche Veränderungen es seit dem letzten Commit gegeben hat.

#### -- 3) __Push__ (lokales Repository auf das Remote Repository hochladen) --
```bash
git push
```
> Ein Push lädt den Commit auf Remote bzw. GitHub hoch.

#### -- Neuen Branch erstellen
```bash
git checkout -b BRANCHNAME
```
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
> Öffnet die angegebene Datei im Remote Repository. Sollte diese Datei aktuell geöffnet sein, wird der Arbeitsbereich auf den Stand des letzten Commits zurückgesetzt.

#### (Später) fetch, log und merge in Teamarbeit
...

### $${\text{\color{blue} Navigation und Erstellung/Einrichtung}}$$

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
> Initialisiert (erstellt) ein lokales Repository im aktuellen Verzeichnis. Alternativ lässt sich auch ein bestimmtes Verzeichnis hinter `init` angeben.

#### -- Lokales Repository mit bestehendem Repository auf GitHub verbinden (nicht nötig nach `clone`) --
```bash
git Remote add origin REPOSITORYLINK
```
> `Remote` = (hier) GitHub, spricht Remote Repository an. Z.B. `git Remote add origin github.com/user/repository123`

> `add` = Fügt neue Verbindung zu einem lokalen Repository hinzu.

> `origin` = Origin ist eine gängige Benennung für das Remote Repository, oder genauer gesagt für die Verbindung zu Remote.

> Ziel-Link = Da anfänglich nur vom lokalen Repository ausgegangen wird, muss ein Ziel angegeben werden.

### $${\text{\color{blue}Einmalig bei dem ersten Push}}$$
#### -- Aktuellen Branch in "main" umbenennen. 
```bash
git branch -M main
```
> `-M` (Move) erzwingt die Änderung, auch wenn Branch "main" schon existiert.
#### -- Verbindung zum Remote herstellen 
```bash
git push -u origin main
```
> `-u` = setzt Upstream-Verbindung (von Local auf Remote) - dies bleibt von hier an die Default-Verbindung bei Push&Pull.

> `origin` = (beliebiger, aber gängiger Name für) Verbindung zu Remote.

> `main` = Name des aktiven Branches.

> `-f` oder `--force` wenn man überschreiben möchte - dies könnte u. U. nötig sein falls Default-Einstellungen etwas blockieren.

> -> Bei späteren Commits geht einfach nur `git push`

### $${\text{\color{blue}Repository von Remote (GitHub) auf Local (PC) Herunterladen}}$$

#### -- (Wenn nicht lokal vorhanden) Repository von GitHub herunterladen und lokal erstellen -> ins Wunschverzeichnis hineinnavigieren
```bash
git clone REPOSITORYLINK
```
> `clone` erstellt ein lokales Repository nach dem Vorbild des Remote, z.B. `git clone github.com/user/repository123`
> Es wird im aktuell geöffneten Ordner ein neuer Ordner mit dem Repository-Namen erstellt.
> Alternativ kann ein Zielordner angegeben werden, der zum Repository gemacht werden soll. 

#### -- (Wenn lokal vorhanden) Repository von GitHub mit lokalem Repository synchronisieren (downstream)
> Sofern noch kein Initial Commit stattgefunden hat, 

#### -- 

### $${\text{\color{blue}Verwaltungsbefehle}}$$

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











