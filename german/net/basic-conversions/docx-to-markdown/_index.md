---
title: Docx zum Markdown
linktitle: Docx zum Markdown
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Word-Dokumente mit Aspose.Words für .NET vom Docx- in das Markdown-Format konvertieren. Schritt-für-Schritt-Anleitung mit Beispielquellcode.
type: docs
weight: 10
url: /de/net/basic-conversions/docx-to-markdown/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET ein Word-Dokument im Docx-Format in Markdown konvertieren. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren der Document- und DocumentBuilder-Objekte

 Initialisieren Sie zunächst die`Document` Objekt und das`DocumentBuilder` Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Inhalt zum Dokument hinzufügen

 Als nächstes verwenden Sie die`DocumentBuilder` Objekt, um dem Dokument Inhalt hinzuzufügen. In diesem Beispiel fügen wir mithilfe von einen einfachen Textabsatz hinzu`Writeln` Methode:

```csharp
builder.Writeln("Some text!");
```

Fügen Sie bei Bedarf gerne komplexere Inhalte wie Überschriften, Tabellen, Listen oder Formatierungen hinzu.

## Schritt 3: Speichern des Dokuments im Markdown-Format

 Um das Dokument im Markdown-Format zu speichern, verwenden Sie die`Save` Methode auf der`Document` Objekt und geben Sie den Pfad und Dateinamen für das Ausgabedokument an. In diesem Beispiel speichern wir es als`"BaseConversions.DocxToMarkdown.md"`:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Word-Dokument im Docx-Format in Markdown konvertiert.

### Beispielquellcode für Docx To Markdown mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Some text!");

	doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");

```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.