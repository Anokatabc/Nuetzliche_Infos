[\(Zurück zur Übersicht\)](https://www.github.com/Anokatabc/Nuetzliche_Infos)<br>

## $${\Huge\text{\color{blue}GitHub-Befehle (Überblick)}}$$
- [A. Workflow und Upload](https://github.com/Anokatabc/Nuetzliche_Infos/blob/main/GitHubBefehle.md#a-%C3%BCblicher-upload-workflow--1-add-stage---2-commit---3-push) - (add, commit, push, checkout)
- [B. Mit Branches arbeiten](https://github.com/Anokatabc/Nuetzliche_Infos/blob/main/GitHubBefehle.md#b-mit-branches-arbeiten) - (checkout, merge, branch)
- [C. Erste Einrichtung](https://github.com/Anokatabc/Nuetzliche_Infos/blob/main/GitHubBefehle.md#c-navigation-und-erstellungeinrichtung) - (init, branch, add origin)
- [D. Erster Push und Verbindung (Upstream)](https://github.com/Anokatabc/Nuetzliche_Infos/blob/main/GitHubBefehle.md#d-einmalig-bei-dem-ersten-push) - (push, --set-upstream)
- [E. Local updaten und herunterladen](https://github.com/Anokatabc/Nuetzliche_Infos/blob/main/GitHubBefehle.md#e-repository-von-remote-github-auf-local-pc-herunterladen) - (clone, pull, reset)
- [F. Verwaltungsbefehle](https://github.com/Anokatabc/Nuetzliche_Infos/blob/main/GitHubBefehle.md#f-verwaltungsbefehle) - (diff, fetch, status, restore)
___
### Grundsätzliches
- `Escape` funktioniert in der Konsole nicht immer, um aus Funktionen/Befehlen auszubrechen - manchmal ist die gefragte Taste `q` (Q). Z. B. nach `git diff` muss man mit `q` beenden.
 ___
### <i><ins>A.</ins> Üblicher Upload-Workflow | 1) add (=Stage) -> 2) commit -> 3) push</i>
#### 1) <ins>Add</ins> - Alle Unterordner "stagen" ("ready for commit")
```bash
git add .
```
> Punkt `.` ist Wildcard für alle Unterordner. Alternativ lassen sich auch spezifische Ordnerpfade oder Dateien angeben -> `git add index.php`

#### 2) <ins>Commit</ins> (in ".git" / im lokalen Repository speichern)
```bash
git commit -m "Stand Commit: Projekt erstellt // Initial Commit"
```
> `-m` = message. Hiermit gibt man an, welche Veränderungen es seit dem letzten Commit gegeben hat.<br>
> Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (d. h. im .git-Ordner).

#### 3) <ins>Push</ins> (lokales Repository auf das remote Repository hochladen)
```bash
git push
```
> Ein Push lädt den Commit auf remote bzw. GitHub hoch.<br>
> Sofern es der erste Push überhaupt ist, am besten einmal Abschnitt D anschauen.

___
### <i><ins>B.</ins> Mit Branches arbeiten</i>
#### Neuen Branch erstellen
```bash
git checkout -b BRANCHNAME
```
> `-b` steht für Branch.<br>
> Erstellt und wechselt zu einem neuen Branch mit dem angegebenen Namen. Alle seit dem letzten Commit vorgenommenen Änderungen werden von diesem neuen Branch übernommen/aufgenommen. Der alte Branch verbleibt auf dem Stand des letzten Commits.

>Branches dienen der Gliederung eines Projekts in einzelne Schritte und/oder Versionen. Sobald die Ziele eines Branches erreicht sind, wird er in der Regel zurück in `main` eingegliedert. <br>
>Man sollte normalerweise nur auf Branches Änderungen vornehmen und diese in `main` einspeisen. So erkennt man wenn Konflikte auftreten sollten und kann diese einzeln betrachten. 

#### Aktiven Branch wechseln
```bash
git checkout BRANCHNAME
```
> Findet in der Regel nur in größeren Projekten Anwendung, um zwischen verschiedenen Bearbeitungsversionen oder Aufgabenbereichen zu wechseln.<br>
> In modernen Projekten wird häufig auch `git switch BRANCHNAME` verwendet.

#### Datei öffnen bzw. geöffnete Datei auf Commit-Stand zurücksetzen
```bash
git checkout DATEINAME
```
> z.B. `git checkout README.md`<br>
> Lädt die angegebene Datei im local Repository. Sollte diese Datei aktuell geöffnet sein, wird der Arbeitsbereich auf den Stand des letzten Commits zurückgesetzt.

#### Fertigen Branch in `main` eingliedern und löschen
>Man befindet sich aktuell auf einem Arbeitsbranch, hat gerade das Ziel des Branches (einen wesentlichen Entwicklungsschritt) erfüllt.<br>
>Man findet den aktuellen Branch heraus mit `git branch` - Es gibt die optionalen Argumente `-a` (gibt alle local und remote Branches zurück) und `-r` (gibt remote Branches zurück).
```bash
git checkout main
git pull
git merge BRANCHNAME
```
>Man wechselt mit `checkout` zurück auf `main`, mit `pull` stellt man sicher, dass `main` mit remote synchronisiert ist. Mit `merge BRANCHNAME` fügt man nun den Branch in `main` ein.<br>
>Als nächstes löscht man nach erfolgreicher Eingliederung üblicherweise den Branch, um das Projekt ordentlich zu halten.
```bash
git branch -d BRANCHNAME
```
>`-d` steht für "delete".<br>
>Sofern der Branch auch auf remote existiert, sollte man ihn auch dort löschen:
```bash
git push origin --delete BRANCHNAME
```
>`push` dient nicht nur zum Hochladen von Dateien - hier gibt er lediglich eine Löschanweisung weiter (`delete`).
___
### <i><ins>C.</ins> Navigation und Erstellung/Einrichtung</i>

#### Lokales Repository finden (wenn vorhanden) -> mit `cd` und `dir` im Terminal herumnavigieren
```bash
git rev-parse --show-toplevel
```
> Ermittelt von einem Kindelement aus (aufwärts) den Ordner, der als Repository markiert ist.<br>
> Das ist der Ordner, in welchem ".git" liegt. Der ist im normalen Datei-Explorer standardmäßig versteckt.

#### Lokales Repository erstellen (initialisieren) -> erst in Wunschverzeichnis hineinnavigieren
```bash
git init
```
> Initialisiert (erstellt) ein lokales Repository im aktuellen Verzeichnis (dieses wird zum local Repository).<br>
> Alternativ lässt sich auch ein bestimmtes Verzeichnis hinter `init` angeben, z.B. `git init C:\Users\Projekte\NeuesRepository`

#### Lokales Repository mit bestehendem Repository auf GitHub verbinden (nicht nötig nach `clone`)
```bash
git remote add origin REPOSITORYLINK
```
> `remote` = (hier) GitHub, spricht remote Repository an. Z.B. `git remote add origin github.com/user/repository123`<br>
> `add` = Fügt neue Verbindung zu einem lokalen Repository hinzu.<br>
> `origin` = "origin" ist eine gängige Benennung für die Verbindung zum remote Repository.<br>
> Ziel-Link = Da anfänglich nur vom lokalen Repository ausgegangen wird, muss ein Ziel angegeben werden.
___
### <i><ins>D.</ins> Einmalig bei dem ersten Push</i>
>Die nachfolgenden Befehle müssen nach Erstellung eines lokalen Repositories und vor dem ersten Pull/Push/Fetch ausgeführt werden (es sei denn es wurde via `clone` erstellt).
#### Aktuellen Branch in "main" umbenennen. 
```bash
git branch -M main
```
> `-M` (Move) erzwingt die Änderung, auch wenn Branch "main" schon existiert.
> Dies ist oft notwendig weil noch "master" als Default-Branch gesetzt ist, was nicht mehr genutzt wird.
#### Verbindung zum remote auf Upstream setzen Option 1: Zusammen mit dem ersten Push
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

#### Verbindung zum remote herstellen Option 2: Separat setzen (ohne Push)
```bash
git branch --set-upstream-to=origin/main
```
 >Eine Upstream-Verbindung muss gesetzt sein, damit `push`, `pull` und `fetch` einwandfrei funktionieren können.<br>
 >Erfordert vorher `git branch -M main` und `git remote add origin REPOSITORYLINK` - d. h. der lokale Branch `main` muss existieren und es muss eine Verbindung zu remote aufgebaut sein
___
### <i><ins>E.</ins> Repository von remote (GitHub) auf local (PC) herunterladen</i>

#### Wenn noch nicht lokal vorhanden -> in gewünschten Elternordner hineinnavigieren
```bash
git clone REPOSITORYLINK
```
> `clone` erstellt ein lokales Repository nach dem Vorbild des remote, z.B. `git clone github.com/user/repository123`<br>
> Es wird im aktuell geöffneten Ordner ein neuer Ordner mit dem Repository-Namen erstellt.
> Alternativ kann statt dem Repositorynamen ein Zielordner angegeben werden, der zum Repository gemacht werden soll, z.B. `git clone REPOSITORYLINK NeuesRepository` (alternativ absoluter Pfad C:\...). Falls nicht vorhanden, wird er mit dem angegebenen Namen erstellt.

#### Wenn lokal vorhanden, verbunden und Upstream gesetzt
```bash
git pull
```
>Lädt den aktuellen Projektstand vom remote Repository (GitHub) herunter und aktualisiert das lokale Repository.<br>
>Hintergründig werden *zwei* Git-Befehle ausgeführt:
><br>`git fetch` (lädt aktuellen Projektstand in den Zwischenspeicher)
><br>`git merge` (aktualisiert das lokale Repository)

#### Wenn lokal veraltet ist und komplett überschrieben werden soll 
>Beispielsweise beim Hin- und Herwechseln zwischen Arbeitsgeräten.
```bash
git fetch origin
git reset --hard origin/main
```
>Mit `fetch origin` den aktuellen Projektstand von GitHub/remote laden. Ohne `origin` würde es auch funktionieren, aber könnte u. U. mehr holen als man möchte, wenn man mit mehreren Remotes verbunden sein sollte.<br>
>Anschließend mit `reset` alle lokalen Dateien durch remote überschreiben lassen. Der aktuelle Bearbeitungsstand geht dabei verloren.
___
### <i><ins>F.</ins> Verwaltungsbefehle</i>

#### Änderungen seit letztem Commit prüfen
```bash
git diff
```
>Listet im Terminal alle Änderungen auf, die seit dem letzten Commit stattgefunden haben.<br>
>Das heißt: Es vergleicht den aktuellen laufenden Bearbeitungsstand mit dem letzten Commit.

#### fetch und mit remote vergleichen (diff origin/main)
```bash
git fetch
```
>Lädt den Stand des remote Repository in eine temporäre Tracking-Datei, damit man Stände vergleichen kann. Hierfür muss eine Upstream-Verbindung bestehen.
```bash
git diff origin/main
```
>Hiermit lässt sich der aktuelle Arbeitsstand mit dem remote Repository vergleichen. Mit Pfeiltaste nach unten lässt sich Zeile für Zeile durch alle Änderungen durchgehen.<br>
>Mit dem Befehl `--no-pager` kann das manuelle Scrollen umgangen werden und alle Änderungen werden komplett in die Konsole geprintet -> `git --no-pager diff origin/main`<br>
>Es kann auch eine konkrete Datei angegeben werden, die man abgleichen möchte -> `git diff origin/main -- index.php`

#### (Später) log
...

#### Sehen was aktuell gestaged ist
```bash
git status
```
> Listet auf, welche Dateien aktuell im Stage Änderungen aufweisen.<br>
> Um herauszufinden, was diese Änderungen (relativ zum lokalen Speicherstand bzw. letzten Commit) sind, gibt es `git diff --cached`

#### Von .git Ordner wiederherstellen (Stand: Letzter Commit)
```bash
git restore .
```
> Stellt Ordnerstruktur aus dem gespeicherten Repository in .git wiederher. Dazu muss kein lokales Repository bestehen - es wird nur der Ordner benötigt.

#### Lokales Repository (unter Windows) löschen -> erst hineinnavigieren
```bash
rmdir /s /q .git
```
> /s = subdirectories

> /q = ohne Bestätigung

> .git = Name des zu löschenden Ordners, hier `.git` bzw. das local Repository

#### Namen und Link des verbundenen remote Repositories herausfinden
> ```bash
>git remote -v
> ```
> >`-v` steht vermutlich für "verbose" und sagt einfach: Gib mir alles über das remote Repository, was du weißt.







