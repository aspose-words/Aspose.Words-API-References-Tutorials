---
title: Konvertierung in PDF 17
linktitle: Konvertierung in PDF 17
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Dokumente in PDF 1.7 konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Konvertieren in PDF 1.7 mit Aspose.Words für .NET. Durch die Konvertierung in PDF 1.7 können Sie PDF-Dateien generieren, die dem PDF 1.7-Standard entsprechen. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments

Laden Sie zunächst das Dokument hoch, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokument angeben.

## Schritt 2: PDF-Konvertierungsoptionen festlegen

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und geben Sie die Version des PDF-Standards an, die Sie verwenden möchten:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Diese Option stellt sicher, dass die generierte PDF-Datei dem PDF 1.7-Standard entspricht.

## Schritt 3: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für die Konvertierung in PDF 17 mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Konvertieren in PDF 1.7 mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach in PDF 1.7 konvertieren.

