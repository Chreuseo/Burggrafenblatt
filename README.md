# Burggrafenblatt – Kurzanleitung für Autorinnen und Autoren

Diese Anleitung ist für alle, die **nur Beiträge schreiben und Bilder einsetzen**. Das Layout und die LaTeX-Befehle werden von der Redaktion gepflegt.

## Welche Datei bearbeite ich?

- Für die aktuelle Ausgabe: `src/02_2026.tex`
- Die Vorlage für neue Ausgaben: `src/main.tex`
- Bilder für Beiträge: `src/img/`

Öffne die Datei der aktuellen Ausgabe und bearbeite nur den **Inhaltsbereich innerhalb von `\begin{document}` und `\end{document}`**. Die Einstellungen und Befehlsdefinitionen am Anfang der Datei gehören zum Kernlayout und sollten nicht verändert werden. Wenn du unsicher bist, kopiere einen vorhandenen Beitragsblock und ersetze darin Überschrift und Text.

## Die wichtigsten Bausteine

### Abschnittsüberschrift

```latex
\Rubrik{Aus dem Semester}
```

Verwende `\Rubrik` für eine große Abschnittsüberschrift, zum Beispiel „Vorwort“ oder „Aus dem Semester“.

### Überschrift für einen Beitrag

```latex
\Artikel{Unser Herbsttreffen in Coburg}
```

Setze `\Artikel` vor den Text des Beitrags. Die Vorlage formatiert die Überschrift automatisch.

### Text und Absätze

Schreibe normalen Text einfach direkt in die Datei. Eine Leerzeile beginnt einen neuen Absatz:

```latex
Das ist der erste Absatz. Er kann über mehrere Zeilen im Editor gehen.

Das ist ein neuer Absatz.
```

Ein einzelner Zeilenumbruch im Editor macht im fertigen Dokument normalerweise **keinen** neuen Absatz. Für einen bewusst erzwungenen Zeilenumbruch kannst du `\\` verwenden, zum Beispiel in einer Grußformel:

```latex
\Grussformel{Viele Grüße\\Max Mustermann}
```

### Text hervorheben

```latex
\textbf{fetter Text}
\textit{kursiver Text}
\emph{betonter Text}
```

### Bild einfügen

Lege das Bild in `src/img/` ab und gib den Dateinamen samt Endung an:

```latex
\Bild{herbsttreffen.jpg}
```

Das Bild wird standardmäßig auf die Breite der aktuellen Spalte angepasst. Eine kleinere Breite kannst du optional als Faktor angeben:

```latex
\Bild[0.7]{herbsttreffen.jpg}
```

`0.7` bedeutet 70 Prozent der Spaltenbreite. Übliche Bildformate sind JPG, PNG und PDF. Verwende möglichst Dateinamen ohne Leerzeichen oder Sonderzeichen.

### Personenprofil mit Bild

Für eine kurze Vorstellung mit Bild gibt es zwei Bausteine. `\BildLinks` setzt das Bild links neben den Text; `\BildRechts` setzt es rechts. Beide Befehle erwarten dieselben vier Angaben: Bildpfad, Rolle oder Funktion, Name und Beschreibung.

```latex
\BildLinks{img/person.jpg}{Kassenwart}{Max Mustermann}{Max kümmert sich um die Finanzen und unterstützt den Verein bei der Planung.}
\BildRechts{img/person.jpg}{Trainerin}{Erika Musterfrau}{Erika organisiert das Training und begleitet die Gruppe bei den Veranstaltungen.}
```

Lege das Bild wie bei `\Bild` in `src/img/` ab. Ein Profil ist ein zusammenhängender Baustein und sollte nicht mitten im Befehl umgebrochen oder verändert werden. Für weitere Personen kannst du den Aufruf kopieren und die vier Angaben ersetzen.

## Spalten und Seiten

Das Layout der Ausgabe legt fest, ob ein Beitrag ein- oder mehrspaltig erscheint. In gleich breiten Textspalten läuft der Text automatisch in die nächste Spalte und bei Bedarf auf der Folgeseite weiter. **Du musst dafür normalerweise keine Spalten- oder Seitenwechsel einfügen.**

Die Befehle `mehrspaltig`, `textspalten`, `\spaltenwechsel`, `\textspaltenwechsel` und `\newpage` steuern das Layout. Bitte ändere oder ergänze sie nur nach Absprache mit der Redaktion.

## Sonderzeichen

Umlaute und `ß` kannst du direkt schreiben. Einige Zeichen haben in LaTeX eine besondere Bedeutung und müssen mit einem Backslash eingegeben werden:

| Zeichen | Eingabe |
|---|---|
| `%` | `\%` |
| `&` | `\&` |
| `$` | `\$` |
| `_` | `\_` |
| `#` | `\#` |

## Ausgabe prüfen

Zum Erstellen der PDF-Datei öffne ein Terminal im Ordner `src` und führe aus:

```bash
pdflatex -interaction=nonstopmode -file-line-error 02_2026.tex
```

Bei einer Fehlermeldung prüfe zuerst, ob alle `{` und `}` zusammenpassen und ob der Bildname einschließlich Endung richtig geschrieben ist. Die PDF-Datei zeigt, wie der Beitrag tatsächlich gesetzt wird.

## Beispiel für einen Beitrag

```latex
\Rubrik{Aus dem Semester}

\Artikel{Unser Herbsttreffen in Coburg}

Beim Herbsttreffen kamen viele Bundesbrüder zusammen. Wir haben gemeinsam
Coburg erkundet und ein schönes Wochenende miteinander verbracht.

\Bild{herbsttreffen.jpg}

Auch der persönliche Austausch kam nicht zu kurz. Wir freuen uns schon auf
das nächste Wiedersehen.
```

# Kompilieren

```bash
pdflatex -interaction=nonstopmode -file-line-error 02_2026.tex
```
