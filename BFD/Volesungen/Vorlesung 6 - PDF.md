---
date: 2024.2.3
tags:
  - "#BFD"
aliases:
---
# 简介
## 基础功能
![[Pasted image 20240203121317.png]]
- 通常的功能：Text/Graphik
- pdf Formular： **XML** Schnittstellen
- 签字：Digital Signature (加密算法，生成唯一数字代码）
- Navigation
	- Bookmarks
	- Links
- XMP für Metadaten
- ***Dokumente*** enthalten *Dictionaries*, *Page Objekte* und *Aktionen*
- **Strukturen** vererben Attribute
- meist hierarchisch -> tree strukture

## Page Objekte
![[Pasted image 20240206135545.png]]
--> 包含以下元素: 
- **Pfadobjekte**: 
	- Kann als Clippingpfad benutzt werden; 
	- beliebige Kombination aus Geraden直线, Rechtecken und kubischen Bezierkurven
- **Textobjekte**: Kombination aus mehreren Buchstaben
- **Externe Objekte** (XObjects): 
	- Externe Objekte werden *außerhalb* des Content-Streams definiert und können anschließend *innerhalb* eines Content-Streams verwendet werden. (外部定义，内部使用)，
	- XObjects werden hauptsächlich dazu benutzt, **Grafiken** in PDF einzubinden.
	- Forms (表单) sind aus Postscript übernommene Datenstrukturen zur Wiederverwendung
-  **Inline-Images**: Eine Möglichkeit um **kleine Grafiken** innerhalb von PDF einzubinden.
- **Shading Objekte**:  底纹
	- Shading Objekte bestehen aus einem beliebigen Umriss 
	- Umriss mit Farbe abhängig von Position im Umriss (z.B. für Farb-verläufe)
- **Annotationen**
	- ![[Pasted image 20240206135738.png]]
	- Text Annotation: Die Annotation wird im geschlossenen Zustand als Icon dargestellt (<mark style="background: #ADCCFFA6;">Kategorien</mark> Comment, Help oder Note)
	- Free Text Annotation: <mark style="background: #ADCCFFA6;">ständig</mark> auf der Seite angezeigt
	- Line Annotation: eine einfache gerade Linie
- **Interaktive Elemente** wie z.B. ein hypermediales Inhaltsverzeichnis

## PDF/A
- für *Langzeitarchivierung*
- geräte**un**abhängig
- abgeschlossen (alle für Renderer notwendigen Ressourcen)
- selbstdokumentierend (元数据, enthält *eigene* Metadaten)
- transparent
	- zugänglich für unmittelbare Auswertungen mittels einfachen Werkzeugen
- *keine technischen Schutzmaßnahmen* (keine Verschlüsselung, Passwörter, usw.)
- offen (Spezifikation öffentlich verfügbar)
- eingesetzt (verbreiteter Einsatz)

>[!Note]
> - kann *nicht* allein die Langzeitarchivierung ermöglichen

## PDF / A-2
Es werden 3 **Konformitätsebenen** vorgesehen:
- **PDF/A-2a**: alle Anforderungen nach ISO 19005-2 sind erfüllt (strukturell, semantisch)
- **PDF/A-2b**: minimale Anforderungen, Erscheinungsbild bleibt erhalten (Langzeitarchivierung).
- **PDF/A-2u**: analog zu 2b, sowie: Verwendung von Unicode alleine
- -> PDF/A-1 Dateien können in /A-2 Dateien eingebettet werden

## PDF/UA
- [什么是PDF/UA](https://pdfmailmerger.com/zh-hans/blog/%E4%BB%80%E4%B9%88%E6%98%AFpdf-ua%EF%BC%9F/#%25e4%25bb%2580%25e4%25b9%2588%25e6%2598%25afpdfua)
- Bf. wird durch Prüfprotokoll (**Matterhorn**) abgesichert 
![[Pasted image 20240206135957.png]]
- Checkpoints (31 Gruppen) betreffen auch spezielle Inhaltsarten und Schnellprüfung
	- ![[Pasted image 20240206135936.png]]
-> jedoch zB kein Mindestkontrastverhältnis, kennt (außer bei Bildern) keine alternative Darstellung
## PDF/UA vs. WCAG
- PDF/UA definiert technische Merkmale und bietet einen technischen Rahmen
- PDF/UA kennt (außer bei Bildern) keine alternative Darstellungen (z.B. Redetext)

# PDF UND BARRIEREFREIHEIT
## Acrobat und Barrierefreiheit
- [什么是Acrobat](https://zh.wikipedia.org/zh-cn/Adobe_Acrobat)
- plugin unterstützt Screenreader
- tagging wird eingeführt
	- Automatisches und manuelles Erstellen
	- Automatisches Prüfen
	- PDF/A (ISO 19005-1) berücksichtigt tagging

## tags in PDF
-> verbesserte Lesbarkeit, logische Leserichtung
- Article `<Art>`: 用于标记文档中的文章或主要内容。
- Figure `<Figure>`: 用于标记文档中的图像或图表。
- **Block-level Elemente: Container**
	- *Division* element `<Div>`: Ein generischer Block oder eine Gruppe von Block-level Elemente
- Spezielle Tags
	- `<Figure>`zeichnet Bilder im Text aus
	- `<Form>`für Formularelemente
	- `<Link>`für Verweise
	- `<Note>`für Annotationen
	- `<Reference>` für Daten innerhalb des Dokuments
- nur wenige Screenreader unterstützen PDF (Jaws 7)

## Serialisierung / Reflow
Dokumente mit Tags können *kompakt* dargestellt werden
- Erhöhung der Lesbarkeit für Sehbehinderte und Dyslexiker
- Die logische Leserichtung wird angewendet

## Barrierefreiheit herstellen
![[Pasted image 20240203153233.png]]
1. 获取pdf
	1. scan-based
	2. selbst pdf
	3. Web pages
2. 如果有需要，添加表单form
3. Tag
4. 检查accessibility
5. 可以的话
	1. lese Reihefolge
	2. tags korriegieren
6. 产生Bookmarks，set Languages

## PDF für Scannerergebnisse
- OCR Anwendungen notwendig (图片文字识别)
- PDF kann sowohl *Bild* als auch *Text* gemeinsam speichern (layer)
- Manuelles Anlegen des Tagstamms sowie automatische Erzeugung von Tags
- Manuelle *Reparatur* von Fehlern durch Tagkontrolle (auch per Screenreader möglich)

## *Artefakte*: außertextliche Elem.
*==Artefakte sind Elemente ohne Zuordnung zum Tagstamm==*
- **Seitennummern：** 文档中的页码通常不需要与标签关联，因为它们是辅助性质的元素，与文档的主要结构无关。
- **Schmucklinien：** 指装饰性的线条或边框，这些通常是用于美化文档的元素。
- **Kommentare：** 文档中的注释或评论通常被视为附加信息，不影响文档的主要结构。
- **Wasserzeichen：** 类似于水印，这些元素通常是在文档上方或下方添加的半透明文本或图像，用于表示文档的状态或机密性。

Die Bearbeitung erfolgt mit dem Touchup-Werkzeug zur Zuordnung/Bearbeitung des Namens bzw. Entfernung von Tags

## Ausgabehilfeprüfung (注意事项) und Bericht
- Vorhandensein alternativer Beschreibungen für Bilder
- Festlegung einer (!) Sprache eines Texts
- Zeichenkodierung bekannt
- Beschriftung der Formularelemente
- Listen- und Tabellenstruktur
- Tabulatorreihenfolge entspricht Ordnungsstruktur

### PAC 2021
PDF Accessibility Checker: *==Freies Prüfwerkzeug für tagged PDF==*
- (Titel, Sprache, Tags, Tabs, Fonts...), 
- auch PAVE m ̈oglich
#### PAC21 Prüfwerkzeug
- Detailbericht („Report“): Mit Hilfe des Detailberichts die einzelnen Fehler im Dokument analysieren.
- Vorschau-Ansicht („Screenreader Preview“): vereinfachte Strukturansicht für die Qualität („Tags“) und der logischen Reihenfolge („LeseReihenfolge“).
- Dokumentstatistik („Document Statistics“): Übersicht der Anzahl der verwendeten StrukturElemente.
- Logische Struktur („Logical Structure“): Expertenansicht des kompletten Tag-Baums, um sich korrespondierende Elemente zu einem Tag im Dokument anzeigen lassen oder die Rollenzuweisungen zu kontrollieren.

### PDF Checking: PAVE & Tingtun
#### PAVE
analysiert das PDF Dokument und bietet diverse Assistenten an, um Tags zu *ergänzen*

#### Tingtun
TingTun prüft PDF gegen WCAG 2.0

### Rolemap/Rollen
- Die Rolemap ordnet *unbekannt Tags* den **vordefinierten** Tags zu
- Rollen werden (heute) auch von Screenreadern erkannt

### Tabellen in PDF
![[Pasted image 20240203160003.png]]

### Formulare in PDF
先读 Linker刻度表的意义再读符号
![[Pasted image 20240203160218.png]]


### Verweise 
- Verweise werden vor den allgemeinen Tags erstellt
- Automatische Erkennung aus OCR Ergebnis möglich (Menü: Erweitert/Verknüpfungen/alle URL erstellen)
- Verweise müssen explizit beschriftet werden (Optionen/Tag aus Auswahl erstellen/Typ „Verweis“

