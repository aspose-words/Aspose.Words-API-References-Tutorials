---
title: Hinzufügen von Inhalten mit DocumentBuilder in Aspose.Words für Java
linktitle: Hinzufügen von Inhalten mit DocumentBuilder
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Masterdokumenterstellung mit Aspose.Words für Java. Eine Schritt-für-Schritt-Anleitung zum Hinzufügen von Text, Tabellen, Bildern und mehr. Erstellen Sie mühelos beeindruckende Word-Dokumente.
type: docs
weight: 26
url: /de/java/document-manipulation/adding-content-using-documentbuilder/
---

## Einführung in das Hinzufügen von Inhalten mit DocumentBuilder in Aspose.Words für Java

In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Aspose.Words für Javas DocumentBuilder verschiedene Arten von Inhalten zu einem Word-Dokument hinzufügen. Wir behandeln das Einfügen von Text, Tabellen, horizontalen Linien, Formularfeldern, HTML, Hyperlinks, Inhaltsverzeichnissen, Inline- und Floating-Bildern, Absätzen und mehr. Lass uns anfangen!

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Words for Java-Bibliothek in Ihrem Projekt eingerichtet ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/words/java/).

## Text hinzufügen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie einen einfachen Textabsatz ein
builder.write("This is a simple text paragraph.");

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

## Tabellen hinzufügen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Beginnen Sie einen Tisch
Table table = builder.startTable();

// Fügen Sie Zellen und Inhalte ein
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// Beenden Sie den Tisch
builder.endTable();

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

## Horizontale Regel hinzufügen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie eine horizontale Regel ein
builder.insertHorizontalRule();

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

## Formularfelder hinzufügen

### Texteingabeformularfeld

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein Texteingabeformularfeld ein
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

### Kontrollkästchen-Formularfeld

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein Kontrollkästchen-Formularfeld ein
builder.insertCheckBox("CheckBox", true, true, 0);

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

### Kombinationsfeld-Formularfeld

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Definieren Sie Elemente für das Kombinationsfeld
String[] items = { "Option 1", "Option 2", "Option 3" };

// Fügen Sie ein Kombinationsfeld-Formularfeld ein
builder.insertComboBox("DropDown", items, 0);

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

## HTML hinzufügen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie HTML-Inhalte ein
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

## Hyperlinks hinzufügen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie einen Hyperlink ein
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com", false);
builder.getFont().clearFormatting();
builder.write(" for more information.");

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

## Hinzufügen eines Inhaltsverzeichnisses

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein Inhaltsverzeichnis ein
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Dokumentinhalt hinzufügen
// ...

// Aktualisieren Sie das Inhaltsverzeichnis
doc.updateFields();

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

## Bilder hinzufügen

### Inline-Bild

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein Inline-Bild ein
builder.insertImage("path/to/your/image.png");

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

### Schwebendes Bild

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein schwebendes Bild ein
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

## Absätze hinzufügen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Legen Sie die Absatzformatierung fest
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Fügen Sie einen Absatz ein
builder.writeln("This is a formatted paragraph.");

// Speichern Sie das Dokument
doc.save("path/to/your/document.docx");
```

## Schritt 10: Bewegen des Cursors

 Sie können die Cursorposition innerhalb des Dokuments mit verschiedenen Methoden steuern, z`moveToParagraph`, `moveToCell`und mehr. Hier ist ein Beispiel:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bewegen Sie den Cursor auf einen bestimmten Absatz
builder.moveToParagraph(2, 0);

// Fügen Sie Inhalte an der neuen Cursorposition hinzu
builder.writeln("This is the 3rd paragraph.");
```

Dies sind einige häufige Vorgänge, die Sie mit Aspose.Words für den DocumentBuilder von Java ausführen können. Weitere erweiterte Funktionen und Anpassungsoptionen finden Sie in der Dokumentation der Bibliothek. Viel Spaß beim Erstellen des Dokuments!


## Abschluss

In diesem umfassenden Leitfaden haben wir die Möglichkeiten von Aspose.Words für Javas DocumentBuilder zum Hinzufügen verschiedener Arten von Inhalten zu Word-Dokumenten untersucht. Wir haben Text, Tabellen, horizontale Linien, Formularfelder, HTML, Hyperlinks, Inhaltsverzeichnis, Bilder, Absätze und Cursorbewegungen behandelt.

## FAQs

### F: Was ist Aspose.Words für Java?

A: Aspose.Words für Java ist eine Java-Bibliothek, die es Entwicklern ermöglicht, Microsoft Word-Dokumente programmgesteuert zu erstellen, zu ändern und zu bearbeiten. Es bietet eine breite Palette von Funktionen für die Dokumenterstellung, Formatierung und das Einfügen von Inhalten.

### F: Wie kann ich meinem Dokument ein Inhaltsverzeichnis hinzufügen?

A: Um ein Inhaltsverzeichnis hinzuzufügen, verwenden Sie das`DocumentBuilder` um ein Inhaltsverzeichnisfeld in Ihr Dokument einzufügen. Stellen Sie sicher, dass Sie die Felder im Dokument aktualisieren, nachdem Sie Inhalte hinzugefügt haben, um das Inhaltsverzeichnis zu füllen. Hier ist ein Beispiel:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein Inhaltsverzeichnisfeld ein
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Dokumentinhalt hinzufügen
// ...

// Aktualisieren Sie das Inhaltsverzeichnis
doc.updateFields();
```

### F: Wie füge ich mit Aspose.Words für Java Bilder in ein Dokument ein?

 A: Mit dem können Sie sowohl Inline- als auch Floating-Bilder einfügen`DocumentBuilder`. Hier sind Beispiele für beides:

#### Inline-Bild:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein Inline-Bild ein
builder.insertImage("path/to/your/image.png");
```

#### Schwebendes Bild:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein schwebendes Bild ein
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### F: Kann ich beim Hinzufügen von Inhalten Text und Absätze formatieren?

 A: Ja, Sie können Text und Absätze mit formatieren`DocumentBuilder`. Sie können Schriftarteigenschaften, Absatzausrichtung, Einrückung und mehr festlegen. Hier ist ein Beispiel:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Legen Sie Schriftart und Absatzformatierung fest
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Fügen Sie einen formatierten Absatz ein
builder.writeln("This is a formatted paragraph.");
```

### F: Wie kann ich den Cursor an eine bestimmte Stelle im Dokument bewegen?

 A: Sie können die Cursorposition mit Methoden wie steuern`moveToParagraph`, `moveToCell`und mehr. Hier ist ein Beispiel:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bewegen Sie den Cursor auf einen bestimmten Absatz
builder.moveToParagraph(2, 0);

// Fügen Sie Inhalte an der neuen Cursorposition hinzu
builder.writeln("This is the 3rd paragraph.");
```

Dies sind einige häufig gestellte Fragen und Antworten, die Ihnen den Einstieg in Aspose.Words für den DocumentBuilder von Java erleichtern sollen. Wenn Sie weitere Fragen haben oder weitere Hilfe benötigen, lesen Sie die[Dokumentation der Bibliothek](https://reference.aspose.com/words/java/) Oder suchen Sie Hilfe bei der Aspose.Words-Community und den Support-Ressourcen.