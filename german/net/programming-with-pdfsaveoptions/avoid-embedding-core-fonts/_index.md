---
title: Vermeiden Sie das Einbetten von Kernschriftarten
linktitle: Vermeiden Sie das Einbetten von Kernschriftarten
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie beim Konvertieren von Word-Dokumenten in PDF mit Aspose.Words für .NET das einfache Einbetten von Schriftarten vermeiden.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion „Grundlegende Schriftarteinbettung vermeiden“ mit Aspose.Words für .NET. Mit dieser Funktion können Sie steuern, ob beim Konvertieren eines Word-Dokuments grundlegende Schriftarten wie Arial, Times New Roman usw. in das PDF eingebettet werden müssen. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments

Laden Sie zunächst das Word-Dokument hoch, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Word-Dokument angeben.

## Schritt 2: PDF-Konvertierungsoptionen festlegen

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und aktivieren Sie die grundlegende Vermeidung der Schriftarteinbettung:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Diese Option steuert, ob Basisschriftarten in das PDF eingebettet werden sollen oder nicht.

## Schritt 3: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Word-Dokuments in PDF durch Angabe von Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für „Vermeiden Sie das Einbetten von Kernschriftarten“ mithilfe von Aspose.Words für .NET

Hier ist der vollständige Quellcode zur Verwendung der Funktion, um die Einbettung von Kernschriftarten mit Aspose.Words für .NET zu vermeiden:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Das Ausgabe-PDF wird nicht in Kernschriftarten wie Arial, Times New Roman usw. eingebettet.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Wenn Sie diese Schritte befolgen, können Sie ganz einfach steuern, ob beim Konvertieren eines Word-Dokuments mit Aspose.Words für .NET Basisschriftarten in die PDF-Datei eingebettet werden sollen.

