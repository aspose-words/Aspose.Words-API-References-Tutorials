---
title: Nach Abschnitten HTML
linktitle: Nach Abschnitten HTML
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie anhand eines vollständigen Codebeispiels, wie Sie ein Word-Dokument mit Aspose.Words für .NET in HTML-Abschnitte aufteilen.
type: docs
weight: 10
url: /de/net/split-document/by-sections-html/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie ein Word-Dokument mithilfe der Funktion „Nach HTML-Abschnitten“ von Aspose.Words für .NET in separate Abschnitte im HTML-Format aufteilen. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und für jeden Abschnitt separate HTML-Dokumente zu generieren.

## Schritt 1: Laden des Dokuments

Geben Sie zunächst das Verzeichnis für Ihr Dokument an und laden Sie das Dokument in ein Document-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Schritt 2: Unterteilen des Dokuments in Abschnitte im HTML-Format

Jetzt legen wir die Speicheroptionen fest, um das Dokument im HTML-Format in Abschnitte zu unterteilen. So geht's:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Beispielquellcode für By Sections HTML mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Nach HTML-Abschnitten“ von Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Rendering.docx");

	
	HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };
	
	
	doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);

```

Mit diesem Code können Sie ein Word-Dokument mit Aspose.Words für .NET in separate Abschnitte im HTML-Format aufteilen.

Jetzt können Sie für jeden Abschnitt des Ausgangsdokuments separate HTML-Dokumente generieren.



