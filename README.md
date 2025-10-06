[Link zum Repository](https://www.github.com/Anokatabc/Nuetzliche_Infos)

# Tipps & Tricks :)

Im Laufe meiner Reise durch das Internet und die IT-Sphäre stoße ich hier und da auf praktische Hilfen oder auf intuitive Erklärungen, die mir sehr beim Verständnis helfen. Eventuell können die mitunter auch Anderen helfen.

## Übersicht
Anleitungen|Beschreibung
---|---
|[1\) GitHub-Guide](https://github.com/Anokatabc/Nuetzliche_Infos/blob/main/GitHubBefehle.md)|Behandelt viele nützliche Informationen und Abläufe bei der Arbeit mit GitHub.
|2|...
|3|...

### Ein paar weniger bekannte Tipps für GitHub-Markdown:<br>
___
### Texthervorhebung
`<sub>TEXT</sub>` -> <sub>TIEFGESTELLT</sub> (<b>sub</b>text)<br>
`<sup>TEXT</sup>` -> <sup>HOCHGESTELLT</sup> (<b>sup</b>ertext)<br>
`<ins>TEXT</ins>` -> <ins>UNTERSTRICHEN</ins><br>

#### Einige klassische HTML-Tags lassen sich auch anwenden: <br>
`<b>Fett</b>` -> <b>Fett</b> (identisch mit `**Fett**` **Fett** oder auch `__Fett__` __Fett__)<br>
`<i>Kursiv</i>` -> <i>Kursiv</i> (identisch mit `*Kursiv*` *Kursiv* oder auch `_Kursiv_` _Kursiv_)
___
### $\color{red}LaTeX$
`${\text{\color{blue}Gefärbter Text mittels LaTeX (Mathematik-Funktionen)}}$` -> ${\text{\color{blue}Gefärbter Text mittels LaTeX (Mathematik-Funktionen)}}$<br>

Der `\text`-Tag ist notwendig für Textinhalte, da Latex per Default im Mathe-Modus ist und alle Leerstellen entfernt und einen unleserlichen Kursivdruck hat. Ohne würde es so aussehen: 
<br>`$\color{yellow}Gefärbter Text mittels Latex$` -> $\color{yellow}Gefärbter Text mittels Latex$

Es gibt auch andere LaTeX-Funktionen, die sich für Texte verwenden lassen. Einzelne Wörter können zum Beispiel $\Huge\text{vergrößert}$ (`$\Huge\text{vergrößert}$`) werden.
___
### Code-Markierung
\`code\` -> `code`<br>
`>Erklärung zum Code` ->
>Erklärung zum Code

#### Kopierbarer Text oder Codebläcke:<br>
\`\`\`<br>Text<br>
\`\`\` <br>->
```
text
```
___
### Horizontale Linien für sinnvolle Gliederung und Untertrennung
`___` (drei Unterstriche) erzeugen so eine Linie:
___
