---
title: Verwenden von Kopf- und Fußzeilen in Aspose.Words für Java
linktitle: Verwenden von Kopf- und Fußzeilen
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie Schritt für Schritt, wie Sie Kopf- und Fußzeilen in Aspose.Words für Java verwenden. Erstellen Sie mühelos professionelle Dokumente.
type: docs
weight: 16
url: /de/java/using-document-elements/using-headers-and-footers/
---

In dieser umfassenden Anleitung führen wir Sie durch den Prozess der Arbeit mit Kopf- und Fußzeilen in Aspose.Words für Java. Kopf- und Fußzeilen sind wesentliche Elemente bei der Dokumentformatierung, und Aspose.Words bietet leistungsstarke Tools, um sie entsprechend Ihren Anforderungen zu erstellen und anzupassen.

Lassen Sie uns nun auf jeden dieser Schritte im Detail eingehen.

## 1. Einführung in Aspose.Words

Aspose.Words ist eine leistungsstarke Java-API, mit der Sie Word-Dokumente programmgesteuert erstellen, bearbeiten und rendern können. Es bietet umfangreiche Funktionen zur Dokumentformatierung, einschließlich Kopf- und Fußzeilen.

## 2. Einrichten Ihrer Java-Umgebung

 Bevor Sie Aspose.Words verwenden, stellen Sie sicher, dass Ihre Java-Entwicklungsumgebung ordnungsgemäß eingerichtet ist. Die notwendigen Setup-Anweisungen finden Sie auf der Aspose.Words-Dokumentationsseite:[Aspose.Words Java-Dokumentation](https://reference.aspose.com/words/java/).

## 3. Erstellen eines neuen Dokuments

Um mit Kopf- und Fußzeilen arbeiten zu können, müssen Sie mit Aspose.Words ein neues Dokument erstellen. Der folgende Code zeigt, wie das geht:

```java
// Java-Code zum Erstellen eines neuen Dokuments
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. Seiteneinrichtung verstehen

 Die Seiteneinrichtung ist entscheidend für die Steuerung des Layouts Ihres Dokuments. Mit können Sie verschiedene Eigenschaften für Kopf- und Fußzeilen festlegen`PageSetup` Klasse. Zum Beispiel:

```java
// Seiteneigenschaften einrichten
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. Unterschiedliche Kopf-/Fußzeile der ersten Seite

Mit Aspose.Words können Sie unterschiedliche Kopf- und Fußzeilen für die erste Seite Ihres Dokuments verwenden. Verwenden`pageSetup.setDifferentFirstPageHeaderFooter(true);` um diese Funktion zu aktivieren.

## 6. Arbeiten mit Headern

### 6.1. Text zu Kopfzeilen hinzufügen

 Mit können Sie Text zu Kopfzeilen hinzufügen`DocumentBuilder`. Hier ist ein Beispiel:

```java
// Text zur Kopfzeile der ersten Seite hinzufügen
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. Bilder in Kopfzeilen einfügen

 Um Bilder in Kopfzeilen einzufügen, können Sie die verwenden`insertImage` Methode. Hier ist ein Beispiel:

```java
// Einfügen eines Bildes in die Kopfzeile
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. Anpassen von Header-Stilen

Sie können Kopfzeilenstile anpassen, indem Sie verschiedene Eigenschaften wie Schriftart, Ausrichtung usw. festlegen, wie in den Beispielen oben gezeigt.

## 7. Arbeiten mit Fußzeilen

### 7.1. Text zu Fußzeilen hinzufügen

 Ähnlich wie bei Kopfzeilen können Sie Fußzeilen mithilfe von Text hinzufügen`DocumentBuilder`. Hier ist ein Beispiel:

```java
// Text zur primären Fußzeile hinzufügen
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// Fügen Sie nach Bedarf Text und Felder ein
```

### 7.2. Bilder in Fußzeilen einfügen

 Um Bilder in Fußzeilen einzufügen, verwenden Sie die`insertImage` Methode, genau wie in Headern.

### 7.3. Anpassen von Fußzeilenstilen

 Passen Sie Fußzeilenstile mit an`DocumentBuilder`ähnlich dem Anpassen von Headern.

## 8. Seitennummerierung

 Sie können Seitenzahlen in Ihre Kopf- und Fußzeilen einfügen, indem Sie Felder wie verwenden`PAGE` Und`NUMPAGES`. Diese Felder werden automatisch aktualisiert, wenn Sie Seiten hinzufügen oder entfernen.

## 9. Urheberrechtsinformationen in Fußzeilen

Um der Fußzeile Ihres Dokuments Urheberrechtsinformationen hinzuzufügen, können Sie eine Tabelle mit zwei Zellen verwenden, von denen eine links und die andere rechts ausgerichtet ist, wie im Codeausschnitt gezeigt.

## 10. Arbeiten mit mehreren Abschnitten

Mit Aspose.Words können Sie mit mehreren Abschnitten innerhalb eines Dokuments arbeiten. Sie können für jeden Abschnitt unterschiedliche Seitenaufbauten und Kopf-/Fußzeilen festlegen.

## 11. Querformatausrichtung

Bei Bedarf können Sie die Ausrichtung bestimmter Abschnitte in den Querformatmodus ändern.

## 12. Kopf-/Fußzeilen aus vorherigen Abschnitten kopieren

Das Kopieren von Kopf- und Fußzeilen aus vorherigen Abschnitten kann beim Erstellen komplexer Dokumente Zeit sparen.

## 13. Speichern Ihres Dokuments

Vergessen Sie nach dem Erstellen und Anpassen Ihres Dokuments nicht, es mit zu speichern`doc.save()` Methode.

## Vollständiger Quellcode
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // Geben Sie an, ob sich die Kopf-/Fußzeilen der ersten Seite von denen anderer Seiten unterscheiden sollen.
        // Sie können zur Angabe auch die Eigenschaft PageSetup.OddAndEvenPagesHeaderFooter verwenden
        // unterschiedliche Kopf-/Fußzeilen für ungerade und gerade Seiten.
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // Fügen Sie ein positioniertes Bild in die obere/linke Ecke der Kopfzeile ein.
        // Der Abstand vom oberen/linken Rand der Seite ist auf 10 Punkte eingestellt.
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // Wir verwenden eine Tabelle mit zwei Zellen, um einen Teil des Textes in die Zeile einzufügen (mit Seitennummerierung).
        // Linksbündig und der andere Teil des Textes (mit Copyright) rechtsbündig.
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // Es verwendet die Felder PAGE und NUMPAGES, um die aktuelle Seitenzahl und viele Seiten automatisch zu berechnen.
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // Machen Sie einen Seitenumbruch, um eine zweite Seite zu erstellen, auf der die primären Kopf-/Fußzeilen angezeigt werden.
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // Dieser Abschnitt benötigt keine andere Kopf-/Fußzeile auf der ersten Seite. Wir benötigen nur eine Titelseite im Dokument.
        //und die Kopf-/Fußzeile für diese Seite wurde bereits im vorherigen Abschnitt definiert.
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // In diesem Abschnitt werden Kopf-/Fußzeilen aus dem vorherigen Abschnitt angezeigt
        // Rufen Sie standardmäßig currentSection.HeadersFooters.LinkToPrevious(false) auf, um diese Seitenbreite abzubrechen
        // ist für den neuen Abschnitt anders, und deshalb müssen wir für eine Fußzeilentabelle andere Zellenbreiten festlegen.
        currentSection.getHeadersFooters().linkToPrevious(false);
        // Wenn wir für diesen Abschnitt den bereits vorhandenen Kopf-/Fußzeilensatz verwenden möchten.
        // Mit einigen geringfügigen Änderungen kann es jedoch sinnvoll sein, Kopf-/Fußzeilen zu kopieren
        // aus dem vorherigen Abschnitt und wenden Sie die erforderlichen Änderungen an der gewünschten Stelle an.
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
Quellcode der Methode copyHeadersFootersFromPreviousSection
```java
    /// <Zusammenfassung>
    /// Klont und kopiert Kopf-/Fußzeilen vom vorherigen Abschnitt in den angegebenen Abschnitt.
    /// </summary>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## Abschluss

In diesem Tutorial haben wir die Grundlagen der Arbeit mit Kopf- und Fußzeilen in Aspose.Words für Java behandelt. Sie haben gelernt, wie Sie Kopf- und Fußzeilen erstellen, anpassen und formatieren sowie andere wichtige Techniken zur Dokumentformatierung anwenden.

 Weitere Einzelheiten und erweiterte Funktionen finden Sie im[Aspose.Words Java-Dokumentation](https://reference.aspose.com/words/java/).

## FAQs

### 1. Wie kann ich der Fußzeile meines Dokuments Seitenzahlen hinzufügen?
 Sie können Seitenzahlen hinzufügen, indem Sie die einfügen`PAGE` Feld mit Aspose.Words in die Fußzeile einfügen.

### 2. Ist Aspose.Words mit Java-Entwicklungsumgebungen kompatibel?
Ja, Aspose.Words bietet Unterstützung für die Java-Entwicklung. Stellen Sie sicher, dass Sie über die erforderlichen Einstellungen verfügen.

### 3. Kann ich die Schriftart und den Stil von Kopf- und Fußzeilen anpassen?
Auf jeden Fall können Sie Schriftarten, Ausrichtung und andere Stile anpassen, um Ihre Kopf- und Fußzeilen optisch ansprechend zu gestalten.

### 4. Ist es möglich, unterschiedliche Kopfzeilen für ungerade und gerade Seiten zu haben?
 Ja, Sie können es verwenden`PageSetup.OddAndEvenPagesHeaderFooter` um unterschiedliche Kopfzeilen für ungerade und gerade Seiten anzugeben.

### 5. Wie beginne ich mit Aspose.Words für Java?
 Besuchen Sie zunächst die[Aspose.Words Java-Dokumentation](https://reference.aspose.com/words/java/) Eine umfassende Anleitung zur Verwendung der API finden Sie hier.