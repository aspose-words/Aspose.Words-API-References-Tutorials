---
title: Zusätzliche Textpositionierung
linktitle: Zusätzliche Textpositionierung
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Platzierung von zusätzlichem Text beim Konvertieren von Word-Dokumenten in PDF mit Aspose.Words für .NET steuern.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/additional-text-positioning/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der zusätzlichen Textpositionierungsfunktion mit Aspose.Words für .NET. Mit dieser Funktion können Sie die Platzierung von zusätzlichem Text beim Konvertieren eines Word-Dokuments in PDF steuern. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments

Laden Sie zunächst das Word-Dokument hoch, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Word-Dokument angeben.

## Schritt 2: PDF-Konvertierungsoptionen festlegen

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und aktivieren Sie die zusätzliche Textpositionierung:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };
```

Diese Option steuert die genaue Platzierung von zusätzlichem Text im PDF.

## Schritt 3: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Word-Dokuments in PDF durch Angabe von Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für zusätzliche Textpositionierung mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zur Verwendung der zusätzlichen Textpositionierungsfunktion mit Aspose.Words für .NET:


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);

```
Wenn Sie diese Schritte befolgen, können Sie die Positionierung von zusätzlichem Text beim Konvertieren eines Word-Dokuments in PDF mit Aspose.Words für .NET einfach steuern.

