[\(Zurück zur Übersicht\)](https://www.github.com/Anokatabc/Nuetzliche_Infos)

## $${\text{\color{blue}GitHub-Befehle (Überblick)}}$$
- [A. Üblicher Upload-Workflow](https://github.com/Anokatabc/Nuetzliche_Infos/edit/main/GitHubBefehle.md#a-%C3%BCblicher-upload-workflow--1-add-stage---2-commit---3-push)
- [E. Verwaltungsbefehle](https://github.com/Anokatabc/Nuetzliche_Infos/blob/main/GitHubBefehle.md#e-verwaltungsbefehle)

### <i><ins>A.</ins> Üblicher Upload-Workflow | 1) add (=Stage) -> 2) commit -> 3) push</i>
#### -- 1) <ins>Add</ins> - Alle Unterordner "stagen" ("ready for commit") --
```bash
git add .
```
> Punkt `.` ist Wildcard für alle Unterordner. Alternativ lassen sich auch spezifische Ordnerpfade oder Dateien angeben -> `git add index.php`

#### -- 2) <ins>Commit</ins> (in ".git" / im lokalen Repository speichern) --
```bash
git commit -m "Stand Commit: Projekt erstellt // Initial Commit"
```
> `-m` = message. Hiermit gibt man an, welche Veränderungen es seit dem letzten Commit gegeben hat.<br>
> Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (d. h. im .git-Ordner).

#### -- 3) <ins>Push</ins> (lokales Repository auf das remote Repository hochladen) --
```bash
git push
```
> Ein Push lädt den Commit auf remote bzw. GitHub hoch.<br>
> Sofern es der erste Push überhaupt ist, am besten einmal Abschnitt C anschauen.

___

#### -- Neuen Branch erstellen
```bash
git checkout -b BRANCHNAME
```
> `-b` steht für Branch.<br>
> Erstellt und wechselt zu einem neuen Branch mit dem angegebenen Namen. Alle seit dem letzten Commit vorgenommenen Änderungen werden auf diesen neuen Branch überschrieben. Der alte Branch verbleibt auf dem Stand des Commits.

#### -- Aktiven Branch wechseln
```bash
git checkout BRANCHNAME
```
> Findet in der Regel nur in größeren Projekten Anwendung, um zwischen verschiedenen Bearbeitungsversionen oder Aufgabenbereichen zu wechseln.<br>
> In modernen Projekten wird häufig auch `git switch BRANCHNAME` verwendet.

#### -- Datei öffnen bzw. geöffnete Datei auf Commit-Stand zurücksetzen
```bash
git checkout DATEINAME
```
> z.B. `git checkout README.md`<br>
> Lädt die angegebene Datei im local Repository. Sollte diese Datei aktuell geöffnet sein, wird der Arbeitsbereich auf den Stand des letzten Commits zurückgesetzt.
___
### <i><ins>B.</ins> Navigation und Erstellung/Einrichtung</i>

#### -- Lokales Repository finden (wenn vorhanden) -> mit `cd` und `dir` im Terminal herumnavigieren --
```bash
git rev-parse --show-toplevel
```
> Ermittelt von einem Kindelement aus (aufwärts) den Ordner, der als Repository markiert ist.<br>
> Das ist der Ordner, in welchem ".git" liegt. Der ist im normalen Datei-Explorer standardmäßig versteckt.

#### -- Lokales Repository erstellen (initialisieren) -> erst in Wunschverzeichnis hineinnavigieren --
```bash
git init
```
> Initialisiert (erstellt) ein lokales Repository im aktuellen Verzeichnis (dieses wird zum local Repository).<br>
> Alternativ lässt sich auch ein bestimmtes Verzeichnis hinter `init` angeben, z.B. `git init C:\Users\Projekte\NeuesRepository`

#### -- Lokales Repository mit bestehendem Repository auf GitHub verbinden (nicht nötig nach `clone`) --
```bash
git remote add origin REPOSITORYLINK
```
> `remote` = (hier) GitHub, spricht remote Repository an. Z.B. `git remote add origin github.com/user/repository123`<br>
> `add` = Fügt neue Verbindung zu einem lokalen Repository hinzu.<br>
> `origin` = "origin" ist eine gängige Benennung für die Verbindung zum remote Repository.<br>
> Ziel-Link = Da anfänglich nur vom lokalen Repository ausgegangen wird, muss ein Ziel angegeben werden.
___
### <i><ins>C.</ins> Einmalig bei dem ersten Push</i>
#### -- Aktuellen Branch in "main" umbenennen. 
```bash
git branch -M main
```
> `-M` (Move) erzwingt die Änderung, auch wenn Branch "main" schon existiert.
> Dies ist oft notwendig weil noch "master" als Default-Branch gesetzt ist, was nicht mehr genutzt wird.
#### -- Verbindung zum remote auf Upstream setzen Option 1: Beim ersten Push
><b>Upstream heißt: "Zu diesem remote Repository gehörst du".</b>
```bash
git push -u origin main
```
> Erfordert bestehenden Commit. Falls noch nicht geschehen -> `git add .` -> `git commit -m "Initial Commit (oder etwas anderes schreiben)"`<br>

> `-u` = setzt Upstream-Verbindung (von local auf remote) - dies bleibt von hier an die Default-Verbindung bei Push&Pull.

> `origin` = Beliebiger, aber üblicher Name für die Verbindung zu remote (GitHub).

> `main` = Name des aktiven Branches.

> `-f` oder `--force` wenn man überschreiben möchte - dies könnte u. U. nötig sein falls Default-Einstellungen etwas blockieren oder Konflikte bestehen (kann im Falle des Letzteren zu Verlusten führen, wenn man einfach überschreibt). <br>

> -> Bei weiteren Updates/Uploads geht nun einfach nur `git push`

#### -- Verbindung zum remote herstellen Option 2: Separat setzen
```bash
git branch --set-upstream-to=origin/main
```
 >Eine Upstream-Verbindung muss gesetzt sein, damit `push`, `pull` und `fetch` einwandfrei funktionieren können.
___
### <i><ins>D.</ins> Repository von remote (GitHub) auf local (PC) herunterladen</i>

#### -- (Wenn nicht lokal vorhanden) -> in Elternordner hineinnavigieren
```bash
git clone REPOSITORYLINK
```
> `clone` erstellt ein lokales Repository nach dem Vorbild des remote, z.B. `git clone github.com/user/repository123`<br>
> Es wird im aktuell geöffneten Ordner ein neuer Ordner mit dem Repository-Namen erstellt.
> Alternativ kann statt dem Repositorynamen ein Zielordner angegeben werden, der zum Repository gemacht werden soll, z.B. `git clone REPOSITORYLINK NeuesRepository` (alternativ absoluter Pfad C:\...). Falls nicht vorhanden, wird er mit dem angegebenen Namen erstellt.

#### -- (Wenn lokal vorhanden, verbunden und Upstream gesetzt)
```bash
git pull
```
>Lädt den aktuellen Projektstand vom remote Repository (GitHub) herunter und aktualisiert das lokale Repository.<br>
>Hintergründig werden *zwei* Git-Befehle ausgeführt:
><br>`git fetch` (lädt aktuellen Projektstand in den Zwischenspeicher)
><br>`git merge` (aktualisiert das lokale Repository)
___
### <i><ins>E.</ins> Verwaltungsbefehle</i>

#### -- Änderungen seit letztem Commit prüfen --
```bash
git diff
```
Listet im Terminal alle Änderungen auf, die seit dem letzten Commit stattgefunden haben.

#### -- fetch und mit remote vergleichen (diff origin/main)
```bash
git fetch
```
>Lädt den Stand des remote Repository in eine temporäre Tracking-Datei, damit man Stände vergleichen kann. Hierfür muss eine Upstream-Verbindung bestehen.
```bash
git diff origin/main
```
>Hiermit lässt sich der aktuelle Arbeitsstand mit dem remote Repository vergleichen. Mit Pfeiltaste nach unten lässt sich Zeile für Zeile durch alle Änderungen durchgehen.<br>
>Mit dem Befehl --no-pager kann das manuelle Scrollen umgangen werden und alle Änderungen werden komplett in die Konsole geprintet -> `git --no-pager diff origin/main`<br>
>Es kann auch eine konkrete Datei angegeben werden, die man abgleichen möchte -> `git diff origin/main -- index.php`

#### -- (Später) log/merge
...

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
> /s = subdirectories

> /q = ohne Bestätigung

> .git = Name des zu löschenden Ordners, hier `.git` bzw. das local Repository



