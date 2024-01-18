>  Zugängliche Grafiken für Menschen mit Blindheit oder Sehbeeinträchtigung und Grafische Notationen

# Agenda:
**Teil 1 + Übung**
1. Grundlagen Grafiken
2. Zugängliche Grafiken
3. Bildbeschreibungen
4. Taktile Grafiken
5. Taktile Interaktion
6. Taktiles Zeichnen

**Teil 2**
- Anwendungsbeispiel
	- Taktile Diagramme
	- (Gebäude)Karten
# Teil 1:
## 1 Grundlagen Grafiken
- verschiedene Grafiktypen und Anwendungszwecke

### Grafiktypen
unterschiedliche Typen mit teils charakteristischen Elementen und unterschiedlichen Funktionen (Zweck) und Kontexten
![[Pasted image 20240116050328.png]]
![[Pasted image 20240116050404.png]]
## 2 Zugängliche Grafiken
- Grafiken = Barriere v.a. für Menschen mit **Blindheit** und **Sehbeeinträchtigung**
- Auch für Menschen mit weiteren Beeinträchtigungen herausfordernd, z.B. Menschen mit **kognitiven Beeinträchtigungen**
- **Kulturell** unterschiedliche Bedeutung von Grafiken (z.B. Farben, Leserichtung, etc.)
- Zugang zu Grafiken unausweichlich für gleichberechtigte, gesellschaftliche Teilhabe, z.B. für Bildung, soziale Bereiche, Social Media, Kultur & Kunst…
- gleichwertigen Zugang durch **alternative Darstellungsweise** des Inhalts gewähren

### Ansätze
> Grafiken für Menschen mit Beeinträchtigungen zugänglich gestalten.

![[Pasted image 20240116073526.png]]
-> Teil 1 剩余部分对前两种方式进行详细说明, 我会在每种方法开始前插入这张图

## 3 Bildbeschreibungen
> Def.: *Alternative* Bildbeschreibungen für Menschen mit Blindheit oder Sehbeeinträchtigung.
-> Alternativen sind in Textform bereitzustellen für jeden Nicht-Text_Inhalt.
-> 使用屏幕阅读器可以朗读powerpoint中图片的替代文字

### Allgemeine Richtlinien -> 对练习很重要
**Wann beschreiben?**
- Prinzipiell: *alle* Nicht-Text-Inhalte
- Ausnahme: reine *Schmuckgrafiken*
- sonst: mindestens Alternativtext unterstützen

**nicht beschrieben werden müssen:**
- Schmuckgrafiken (reine Dekorationselemente)
- Informationen, die auf andere Weise (z.B. Bildunterschrift, umliegender Text) zugänglich sind.

**Was beschreiben?** 
- Grafiktyp
- Absicht/Zweck des Bildes
- Ort, Objekte, Gebäude, Menschen
- Farben (wenn relevant)
- Atomsphäre
- Handlungen
- Kontext ()
![[Pasted image 20240116075745.png]]

**Context is the key**
- Inhalte der Beschreibung hängen vom Kontext des Bildes ab.
- relevant?
- verfügbare Informationen im Kontext

**Wie beschreiben?**
- vom Allgemeinen zum Speziellen
- zielgruppenangepasst (Vokabular, Expertise...)
- objektiv (keine Interpretationen, Meinungen, Auslassungen oder Emotionen)
- kurz, prägnant und verständlich -> inhaltstragende Wörter, Aufzählungen
- Ton und Sprache (Terminologie, beschreibend, aktiv Verben)
 
大致流程:
![[Pasted image 20240116080404.png]]

### Detailgrad
**unterschiedliche Beschreibungen bereitstellen:**
- unterscheidbar nach Detaillierungsgrad
- Nutzende können selbst entscheiden, ob Grafik für sie *relevant* ist und detaillierte Informationen von *Interesse* sind.
- Drill-Down Organisation:
	- 1. **Alternativtext** : *kurzer* *Überblick* max. 1-2 Sätze
	- 2. **Bildunterschrift** : *kurze* Beschreibung mit zusätzlichen Informationen, die nicht auf visuelle Elemente fokussiert sein muss (für alle Menschen sichtbar)
	- 3. **Bildbeschreibung** : *detaillierte* Beschreibung der Bildinhalte, was den Zugang zu visuellen Konzepten unterstützt.

-> 按照包含细节的多少, 划分为三类

### Methoden zur Bildbeschreibung
#### Bereitstellung mit HTML
![[Pasted image 20240116082556.png]]
![[Pasted image 20240116082643.png]]
![[Pasted image 20240116082726.png]]
![[Pasted image 20240116082811.png]]
![[Pasted image 20240116082841.png]]

#### Bereitstellung mit SVG
##### Barrierefreies SVG
- Erhöht Verständnis von Grafiken für alle Betrachtenden
- Lesbarkeit ohne Grafikprogramm möglich
- alle Elemente semantisch kennzeichnen:
	- wenn möglich Basistypen statt `path` verwenden (z.B. `circle, rect, line, polygon...`) 
	- Textalternativen und -beschreibungen: title, desc, meta
	- Gruppierungen von Elementen mit `g` 
	- sinnvolle Wiederverwendung gleichbedeutender separat definierter Elemente mit `use`
	- Objekttransformationen vermeiden (Linienstile, Schriftgröße etc. werden mitskaliert.)
- externe SCG Grafik kann via `<img>`-Tag wie Pixelgrafik eingebunden werden (Alternativtext).
	- `<img src="beispiel.svg" alt ="eine beispielhafte Grafik"/>`
- Inline SVG : `<Title>` und `<Desc>` zur Beschreibung der Elemente + arialabelledby im svg-tag (Besserer Browsersupport)
- `tabindex` kann für *einzelne* Elemente festgelegt werden, sodass SVG-Datei **navigierbar** wird
![[Pasted image 20240118210310.png]]

#### Bereitstellung mit Editoren
##### Bildbeschreibung hinzufügen
- von diversen Programmen bspw. Word,  Powerpoint, Acrobat Reader DC unterstützt
- Beschreibungen gegebenenfalls in separater Datei mitliefern (mit entsprechendem Verweis darauf.)
- ![[Pasted image 20240118210609.png]]

#### Herausforderungen
- Oft nur eine mögliche Interpretation -> subjektiv, abhängig von Wissen und Fähigkeiten des Erstellenden.
- Notationscharakteristik schwer verbalisierbar.
- z.B. komplexe Darstellungen, Schalkreis(Elektrotechnik), UML, Aufbau Experiment
- Detaillierungsgrad (Farben? Hintergrundwissen? -> 考虑读者的感受)
- Erstellung sehr aufwändig, bspw. AGSBS -> meist manuelle Erstellung von Personen mit Fachexpertise
- Verstehen komplexer Beschreibungen is anstrengend und benötigt viel Zeit.

## 4 Taktile Grafiken
### Einführung und Gestaltung
![[Pasted image 20240118213753.png]]
触觉感受, 首先尝试把手指静止放在某种材料上, 然后开始移动, 看感受有什么不同。-->MBO中讲的类似, 触觉需要西东手指

### Definition: Taktile Grafiken
> fühlbare Grafiken, die mit dem Tastsinn wahrgenommen werden können.
> bestehen aus erhabenen Punktsymbolen, Linien und Texturen -> Unterscheidung 
> häufig in Kombination mit Braille-Beschriftungen.
> verschiedene Erstellungsverfahren und Techniken verfügbar

### Distribution Schwellpapier
- Druck auf Spezialpapier -> gleichmäßig erhitzen
- **Heiligkeitswert** entspricht Schwellhöhe: Je dunkler, desto höher geschwellt.

**Vorteil**: 
- Handelsübliche Laserprinter verwendbar
- Glatte Linienverläufe
- Unterschiedliche Reliefhöhen
- Hohe Auflösung

**Nachteil**:
- Schlecht für Braille-Schrift -> 因为是用Fuser对智障进行加工, 不适用盲文的打印, 有点大材小用的感觉
- keine harten Kanten
- benötigt Spezialgerät zum "Schwellen" (Fuser,  熔凝器)
- Schwellpapier ist preisintensiv (ca. 1€ pro A4 Blatt)
![[Pasted image 20240118215843.png]]
### Distribution Braille Drucker
- Für Braille-Schrift-Druck **optimiert**
- Punktabstand lässt sich verändern (Braille-Schrift, äquidistant)

**Vorteile:**
- tiefe Prägung
- variable Auflösung
- kann aus Text generiert werden
- Duplexdruck möglich -> 双面打印

**Nachteile:**
- geringe Auflösung (ca. 10 dpi)
- nur eine Reliefhöhe

![[Pasted image 20240118220430.png]]

### Distribution Taktile Druker
- für Grafikdruck optimiert
- automatische Umsetzung von Helligkeitswerten in Reliefhöhen. (Reliefkarte:  地形图)

**Vorteil:**
- 8 Stufen von Prägungstiefen (praktisch max.3 unterscheidbar)
- scharfe Kanten und Linien
- große Papierformate
- kombinierbar mit Schwarzschrift, Farben

**Nachteil:**
- Auflösung (ca. 20 dpi)
- kostenintensive Hardware
- unüblicher als Braille-Druck -> geringe Verfügbarkeit









