---
title: Markdown-Dokument lesen
linktitle: Markdown-Dokument lesen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie Markdown-Dokumente mit Aspose.Words für .NET lesen.
type: docs
weight: 10
url: /de/net/working-with-markdown/read-markdown-document/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie ein Markdown-Dokument mit Aspose.Words für .NET lesen. Markdown ist eine leichte Auszeichnungssprache, die zum Formatieren von reinem Text verwendet wird.

## Schritt 1: Lesen des Markdown-Dokuments

 Zuerst verwenden wir die`Document` Klasse zum Lesen des Markdown-Dokuments. Wir müssen den Pfad der zu lesenden Markdown-Datei angeben.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Quotes.md");
```

## Schritt 2: Entfernen Sie die Headerformatierung

Wir können die Formatierung aus der Kopfzeile im letzten Absatz des Dokuments entfernen. In diesem Beispiel weisen wir dem Absatz den Stil „Zitat“ zu.

```csharp
Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
paragraph.ParagraphFormat.Style = doc.Styles["Quote"];
```

## Schritt 3: Speichern des Dokuments

Abschließend können wir das Dokument im gewünschten Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
```

### Beispielquellcode zum Lesen eines Markdown-Dokuments mit Aspose.Words für .NET


```csharp
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Quotes.md");

	// Entfernen wir die Überschriftenformatierung aus einem Zitat im allerletzten Absatz.
	Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
	paragraph.ParagraphFormat.Style = doc.Styles["Quote"];

	doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
            
```

Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie ein Markdown-Dokument mit Aspose.Words für .NET lesen.

