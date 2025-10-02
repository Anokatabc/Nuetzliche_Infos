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

> remote = GitHub, spricht remote repository an.

> add = fügt neue Verbindung zu einem lokalen Repository hinzu

> origin = beliebige Benennung der Verbindung, üblicherweise "origin" für erste/normale Verbindung

> Link = da vom lokalen Repository ausgegangen wird (übers Terminal), muss ein Ziel angegeben sein.

```bash
git remote add origin REPOSITORYLINK
```


### Hochladen und Synchronisieren (add (=Stage) -> commit -> push)

#### -- (einmalig vor dem ersten Push) aktuellen Branch in "main" umbenennen. --

M (Move) erzwingt die Änderung, auch wenn Branch "main" schon existiert.

```bash
git branch -M main
```

u = setzt Upstream-Verbindung (von lokal auf remote) - dies bleibt von hier an die Default-Verbindung bei Push&Pull

origin" = (beliebiger, aber gängiger Name für) Verbindung zu remote

main" = Name des aktiven Branches
 
f` oder `--force` wenn man überschreiben möchte

Bei späteren Commits geht einfach nur "git push"

```bash
git push -u origin main
```

#### -- Alle Unterordner "stagen" ("ready for commit") --

```bash
git add .
```


#### -- Commit --

Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (.git-Ordner)

m = Message. Angeben welche Veränderungen es seit dem letzten Commit gegeben hat.

```bash
git commit -m "Stand Commit: Projekt erstellt"
```

#### -- Pushen --





### Repository von Remote (GitHub) auf Local (PC) Herunterladen

#### -- (Wenn nicht lokal vorhanden) Repository von GitHub herunterladen und lokal erstellen -> ins Wunschverzeichnis hineinnavigieren
clone erstellt ein lokales Repository nach dem Vorbild des Remote
```bash
git clone REPOSITORYLINK
```
#### -- (Wenn lokal vorhanden) Repository von GitHub mit lokalem Repository synchronisieren (downstream)
Sofern noch kein

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

s = subdirectories

q = ohne Bestätigung

git = \[Dateiordner]

```bash
rmdir /s /q .git
```











