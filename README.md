````markdown
# Übersicht: LaTeX-Textformatierung in Markdown

# Fett und Kursiv
$\textbf{Text}$
- **Kursiv:** `\textit{Text}` → $\textit{Text}$
- **Mit \mathbf{}:** `\mathbf{Text}` → $\mathbf{Text}$ (nur Buchstaben, keine Sonderzeichen)
- **Mit \mathit{}:** `\mathit{Text}` → $\mathit{Text}$

## Unterstreichen
- `\underline{Text}` → $\underline{Text}$

## Durchstreichen (MathJax only)
- `\cancel{Text}` → $\cancel{Text}$ (nur mit aktiviertem cancel-Paket)

## Schriftarten
- **Serifenlos:** `\textsf{Text}` → $\textsf{Text}$
- **Monospace:** `\texttt{Text}` → $\texttt{Text}$
- **Roman:** `\textrm{Text}` → $\textrm{Text}$
- **Small Caps:** `\textsc{Text}` → $\textsc{Text}$

## Schriftgröße
- `\tiny{Text}` → {\tiny Text}
- `\scriptsize{Text}` → {\scriptsize Text}
- `\footnotesize{Text}` → {\footnotesize Text}
- `\small{Text}` → {\small Text}
- `\normalsize{Text}` → {\normalsize Text}
- `\large{Text}` → {\large Text}
- `\Large{Text}` → {\Large Text}
- `\LARGE{Text}` → {\LARGE Text}
- `\huge{Text}` → {\huge Text}
- `\Huge{Text}` → {\Huge Text}

*(Hinweis: Schriftgrößen funktionieren meist nur in Block-Math, und nicht überall)*

## Farben
- `\color{red}Text` → {\color{red}Text}
- `\textcolor{blue}{Text}` → $\textcolor{blue}{Text}$
- `\colorbox{yellow}{Text}` → $\colorbox{yellow}{Text}$

*(Farben funktionieren nur, wenn das color-Paket unterstützt wird – z.B. KaTeX, MathJax)*

## Sonstiges
- **Hochgestellt:** `Text^{hoch}` → $Text^{hoch}$
- **Tiefgestellt:** `Text_{tief}` → $Text_{tief}$

---

## Beispiel für kombinierte Formatierung

```markdown
$\textbf{\textcolor{red}{Fett und rot}}$
```

---

## Wichtige Hinweise
- **Nur innerhalb von Math-Umgebungen!** (`$...$` oder `$$...$$`)
- **Nicht alle Befehle werden überall unterstützt.** GitHub und Jupyter verwenden KaTeX/MathJax, die meisten Befehle aus dieser Liste funktionieren dort.
- **Für normales Markdown außerhalb von Math-Umgebungen** gelten nur die Standard-Formatierungen wie `**fett**`, `_kursiv_`, usw.

---

## Übersicht als Tabelle

| Befehl                 | Beispiel                     | Ergebnis         |
|------------------------|-----------------------------|------------------|
| \textbf{Text}          | $\textbf{Text}$             | **Text**         |
| \textit{Text}          | $\textit{Text}$             | *Text*           |
| \underline{Text}       | $\underline{Text}$          | _Text_           |
| \textcolor{red}{Text}  | $\textcolor{red}{Text}$     | Text             |
| \color{blue}Text       | {\color{blue}Text}          | Text             |
| \texttt{Text}          | $\texttt{Text}$             | `Text`           |
| \textsf{Text}          | $\textsf{Text}$             | Text             |
| \cancel{Text}          | $\cancel{Text}$             | ~~Text~~         |
| \tiny{Text}            | {\tiny Text}                | Text             |
| \Huge{Text}            | {\Huge Text}                | Text             |

````



###### -- Lokales Repository finden (mit cd und dir herumnavigieren)

**git rev-parse --show-toplevel**



##### -- Lokales Repository relokalisieren (u. a. löschen) -> erst hineinnavigieren

 		*/s = subdirectories*

 		*/q = ohne Bestätigung*

 		*.git = \[Dateiordner]*

<mark>**rmdir /s /q .git**</mark>



##### -- Lokales Repository erstellen (initialisieren) -> erst hineinnavigieren

$\color{red}\textbf{git init}$



##### -- Lokales Repository mit bestehendem R. auf GitHub verbinden.

 	*remote = GitHub, spricht remote repository an.*

 	*add = fügt neue Verbindung zu einem lokalen Repository hinzu*

 	*origin = beliebige Benennung der Verbindung, üblicherweise "origin" für erste/normale Verbindung*

 	*Link = da vom lokalen Repository ausgegangen wird (übers Terminal), muss ein Ziel angegeben sein.*

**git remote add origin REPOSITORYLINK**



##### -- Alle Unterordner "stagen" ("ready for commit")

**git add .**



##### -- Commit

 	*Der Commit selbst speichert den aktuellen Projektstand im lokalen Repository (.git-Ordner)*

 	*-m = Message. Angeben welche Veränderungen es seit dem letzten Commit gegeben hat.*

**git commit -m "Stand Commit: Projekt erstellt"**



##### -- (einmalig beim ersten Push) aktuellen Branch in "main" umbenennen.

 	*-M erzwingt die Änderung.*

**git branch -M main**



##### -- Pushen

	*-u = setzt upstream-Verbindung (von lokal auf remote).*

	*"origin" = Verbindung zu remote*

	*"main" = aktiver Branch*

	*-f oder --force wenn man überschreiben möchte*

	*-Bei späteren Commits geht einfach nur "git push"*

**git push -u origin main**



##### -- Änderungen seit letztem Commit prüfen

**git diff**



##### -- Sehen was aktuell gestaged ist

**git status**



##### -- Von .git Ordner wiederherstellen (Stand: Letzter Commit)

**git restore .**

