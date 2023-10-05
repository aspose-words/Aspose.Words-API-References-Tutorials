---
title: Dokumente als Markdown in Aspose.Words für Java speichern
linktitle: Dokumente als Markdown speichern
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Word-Dokumente mit Aspose.Words für Java in Markdown konvertieren. Diese Schritt-für-Schritt-Anleitung behandelt die Tabellenausrichtung, die Bildbearbeitung und mehr.
type: docs
weight: 18
url: /de/java/document-loading-and-saving/saving-documents-as-markdown/
---

## Einführung in das Speichern von Dokumenten als Markdown in Aspose.Words für Java

In dieser Schritt-für-Schritt-Anleitung zeigen wir, wie Sie Dokumente mit Aspose.Words für Java als Markdown speichern. Markdown ist eine leichte Auszeichnungssprache, die häufig zum Formatieren von Textdokumenten verwendet wird. Mit Aspose.Words für Java können Sie Ihre Word-Dokumente ganz einfach in das Markdown-Format konvertieren. Wir werden verschiedene Aspekte des Speicherns von Markdown-Dateien behandeln, einschließlich der Ausrichtung von Tabelleninhalten und der Handhabung von Bildern.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Java Development Kit (JDK) auf Ihrem System installiert.
-  Aspose.Words für Java-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/words/java/).

## Schritt 1: Erstellen eines Word-Dokuments

Beginnen wir mit der Erstellung eines Word-Dokuments, das wir später in das Markdown-Format konvertieren. Sie können dieses Dokument an Ihre Anforderungen anpassen.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie eine Tabelle mit zwei Zellen ein
builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
builder.write("Cell1");

builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.write("Cell2");

// Speichern Sie das Dokument als Markdown
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
doc.save("output.md", saveOptions);
```

 In diesem Beispiel erstellen wir eine einfache Tabelle mit zwei Zellen und legen die Ausrichtung der Absätze innerhalb dieser Zellen fest. Dann speichern wir das Dokument als Markdown mit`MarkdownSaveOptions`.

## Schritt 2: Passen Sie die Ausrichtung des Tabelleninhalts an

Mit Aspose.Words für Java können Sie die Ausrichtung von Tabelleninhalten beim Speichern als Markdown anpassen. Sie können den Tabelleninhalt links, rechts oder mittig ausrichten oder ihn automatisch anhand des ersten Absatzes in jeder Tabellenspalte ermitteln lassen.

So passen Sie die Ausrichtung des Tabelleninhalts an:

```java
// Stellen Sie die Ausrichtung des Tabelleninhalts auf links ein
saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
doc.save("left_alignment.md", saveOptions);

// Stellen Sie die Ausrichtung des Tabelleninhalts auf rechts ein
saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
doc.save("right_alignment.md", saveOptions);

// Stellen Sie die Ausrichtung des Tabelleninhalts auf Mitte ein
saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
doc.save("center_alignment.md", saveOptions);

//Stellen Sie die Ausrichtung des Tabelleninhalts auf „Automatisch“ ein (bestimmt durch den ersten Absatz).
saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
doc.save("auto_alignment.md", saveOptions);
```

 Durch die Änderung der`TableContentAlignment` Mit der Eigenschaft können Sie steuern, wie der Inhalt in Tabellen bei der Konvertierung in Markdown ausgerichtet wird.

## Schritt 3: Umgang mit Bildern

 Um Bilder in Ihr Markdown-Dokument aufzunehmen, müssen Sie den Ordner angeben, in dem sich die Bilder befinden. Mit Aspose.Words für Java können Sie den Bilderordner im festlegen`MarkdownSaveOptions`.

So legen Sie den Bilderordner fest und speichern das Dokument mit Bildern:

```java
// Laden Sie ein Dokument mit Bildern
Document doc = new Document("document_with_images.docx");

// Legen Sie den Pfad zum Bilderordner fest
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
saveOptions.setImagesFolder("images_folder/");

// Speichern Sie das Dokument mit Bildern
doc.save("document_with_images.md", saveOptions);
```

 Unbedingt austauschen`"document_with_images.docx"` mit dem Pfad zu Ihrem Word-Dokument mit Bildern und`"images_folder/"` mit dem tatsächlichen Pfad zu dem Ordner, in dem Ihre Bilder gespeichert sind.

## Vollständiger Quellcode zum Speichern von Dokumenten als Markdown in Aspose.Words für Java

```java
public void autoTableContentAlignment() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
	builder.write("Cell1");
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
	builder.write("Cell2");
	// Alle Absätze in der Tabelle werden ausgerichtet.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
	{
		saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
	}
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);
	// Die Ausrichtung wird in diesem Fall dem ersten Absatz in der entsprechenden Tabellenspalte entnommen.
	saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
}
@Test
public void setImagesFolder() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Image bullet points.docx");
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions(); { saveOptions.setImagesFolder("Your Directory Path" + "Images"); }
	try(ByteArrayOutputStream stream = new ByteArrayOutputStream())
	{
		doc.save(stream, saveOptions);
	}
}
```

## Abschluss

In diesem Leitfaden haben wir untersucht, wie Sie Dokumente mit Aspose.Words für Java als Markdown speichern. Wir haben die Erstellung eines Word-Dokuments, die Anpassung der Tabelleninhaltsausrichtung und den Umgang mit Bildern in Markdown-Dateien behandelt. Sie können Ihre Word-Dokumente jetzt effizient in das Markdown-Format konvertieren, sodass sie für verschiedene Veröffentlichungsplattformen und Dokumentationsanforderungen geeignet sind.

## FAQs

### Wie installiere ich Aspose.Words für Java?

 Aspose.Words für Java kann installiert werden, indem Sie die Bibliothek in Ihr Java-Projekt einbinden. Sie können die Bibliothek herunterladen unter[Hier](https://releases.aspose.com/words/java/) und befolgen Sie die Installationsanweisungen in der Dokumentation.

### Kann ich komplexe Word-Dokumente mit Tabellen und Bildern in Markdown konvertieren?

Ja, Aspose.Words für Java unterstützt die Konvertierung komplexer Word-Dokumente mit Tabellen, Bildern und verschiedenen Formatierungselementen in Markdown. Sie können die Markdown-Ausgabe entsprechend der Komplexität Ihres Dokuments anpassen.

### Wie kann ich mit Bildern in Markdown-Dateien umgehen?

 Um Bilder in Markdown-Dateien einzubinden, legen Sie den Bildordnerpfad mit fest`setImagesFolder`Methode in`MarkdownSaveOptions`. Stellen Sie sicher, dass die Bilddateien im angegebenen Ordner gespeichert sind und Aspose.Words für Java die Bildverweise entsprechend behandelt.

### Gibt es eine Testversion von Aspose.Words für Java?

Ja, Sie können eine Testversion von Aspose.Words für Java von der Aspose-Website erhalten. Mit der Testversion können Sie die Funktionen der Bibliothek testen, bevor Sie eine Lizenz erwerben.

### Wo finde ich weitere Beispiele und Dokumentation?

 Weitere Beispiele, Dokumentation und detaillierte Informationen zu Aspose.Words für Java finden Sie unter[Dokumentation](https://reference.aspose.com/words/java/).