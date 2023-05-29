---
title: Nach Überschriften HTML
linktitle: Nach Überschriften HTML
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes der By Heading HTML-Funktion von Aspose.Words für .NET
type: docs
weight: 10
url: /de/net/split-document/by-headings-html/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie ein Word-Dokument mithilfe der Funktion „Nach HTML-Überschrift“ von Aspose.Words für .NET in kleinere Teile aufteilen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und separate HTML-Dokumente basierend auf der Überschrift zu generieren.

## Schritt 1: Laden des Dokuments

Geben Sie zunächst das Verzeichnis für Ihr Dokument an und laden Sie das Dokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Schritt 2: Unterteilen des Dokuments nach Überschrift im HTML-Format

Jetzt legen wir die Speicheroptionen fest, um das Dokument basierend auf der Überschrift im HTML-Format in kleinere Teile aufzuteilen. Hier ist wie:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Teilen Sie das Dokument in kleinere Teile auf, in diesem Fall nach Titel.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Beispielquellcode für By Headings HTML mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Nach HTML-Überschrift“ von Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Teilen Sie ein Dokument in kleinere Teile auf, in diesem Fall nach Überschrift.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Mit diesem Code können Sie ein Word-Dokument mithilfe von Aspose.Words für .NET basierend auf Überschriften in kleinere Teile aufteilen. Anschließend können Sie für jeden Teil separate HTML-Dokumente generieren.

