---
title: Zusammenfügen und Anhängen von Dokumenten in Aspose.Words für Java
linktitle: Zusammenfügen und Anhängen von Dokumenten
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für Java Dokumente mühelos zusammenfügen und anhängen. Behalten Sie die Formatierung bei, verwalten Sie Kopf- und Fußzeilen und vieles mehr.
type: docs
weight: 30
url: /de/java/document-manipulation/joining-and-appending-documents/
---

## Einführung in das Zusammenfügen und Anhängen von Dokumenten in Aspose.Words für Java

In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.Words for Java-Bibliothek Dokumente verknüpfen und anhängen. Sie erfahren, wie Sie mehrere Dokumente nahtlos zusammenführen und dabei Formatierung und Struktur beibehalten.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass in Ihrem Java-Projekt die Aspose.Words for Java-API eingerichtet ist.

## Optionen zum Zusammenfügen von Dokumenten

### Einfaches Anhängen

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Mit Importformatoptionen anhängen

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### An leeres Dokument anhängen

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Mit Seitenzahlkonvertierung anhängen

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // Konvertieren Sie NUMPAGES-Felder
dstDoc.updatePageLayout(); // Aktualisieren Sie das Seitenlayout, um die korrekte Nummerierung zu gewährleisten
```

## Umgang mit verschiedenen Seiteneinrichtungen

Beim Anhängen von Dokumenten mit unterschiedlichen Seiteneinrichtungen:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// Stellen Sie sicher, dass die Seiteneinrichtungseinstellungen mit dem Zieldokument übereinstimmen
```

## Dokumente mit unterschiedlichen Stilen zusammenfügen

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## Intelligentes Stilverhalten

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## Einfügen von Dokumenten mit DocumentBuilder

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Beibehaltung der Quellennummerierung

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Umgang mit Textfeldern

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Kopf- und Fußzeilen verwalten

### Verknüpfen von Kopf- und Fußzeilen

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Verknüpfung von Kopf- und Fußzeilen aufheben

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Abschluss

Aspose.Words für Java bietet flexible und leistungsstarke Tools zum Zusammenfügen und Anhängen von Dokumenten, unabhängig davon, ob Sie die Formatierung beibehalten, verschiedene Seiteneinstellungen verwalten oder Kopf- und Fußzeilen verwalten müssen. Experimentieren Sie mit diesen Techniken, um Ihre spezifischen Anforderungen an die Dokumentenverarbeitung zu erfüllen.

## FAQs

### Wie kann ich Dokumente mit unterschiedlichen Stilen nahtlos zusammenfügen?

 Um Dokumente mit unterschiedlichen Stilen zu verbinden, verwenden Sie`ImportFormatMode.USE_DESTINATION_STYLES` beim Anhängen.

### Kann ich die Seitennummerierung beim Anhängen von Dokumenten beibehalten?

 Ja, Sie können die Seitennummerierung beibehalten, indem Sie die verwenden`convertNumPageFieldsToPageRef` Methode und Aktualisierung des Seitenlayouts.

### Was ist Smart Style Behavior?

 Smart Style Behavior hilft dabei, einheitliche Stile beim Anhängen von Dokumenten beizubehalten. Benutze es mit`ImportFormatOptions` für bessere Ergebnisse.

### Wie kann ich beim Anhängen von Dokumenten mit Textfeldern umgehen?

Satz`importFormatOptions.setIgnoreTextBoxes(false)` um beim Anhängen Textfelder einzuschließen.

### Was passiert, wenn ich Kopf- und Fußzeilen zwischen Dokumenten verknüpfen bzw. die Verknüpfung aufheben möchte?

 Sie können Kopf- und Fußzeilen mit verknüpfen`linkToPrevious(true)` oder die Verknüpfung aufheben`linkToPrevious(false)` wie benötigt.