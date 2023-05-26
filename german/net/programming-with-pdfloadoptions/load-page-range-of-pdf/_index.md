---
title: Seitenbereich von PDF laden
linktitle: Seitenbereich von PDF laden
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Laden eines bestimmten PDF-Seitenbereichs mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET einen bestimmten Seitenbereich aus einem PDF-Dokument laden. Folgen Sie den unteren Schritten:

## Schritt 1: Laden einer Reihe von PDF-Seiten

Verwenden Sie den folgenden Code, um einen bestimmten Seitenbereich aus einem PDF-Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 In diesem Beispiel laden wir die erste Seite des PDF-Dokuments. Sie können die Werte von ändern`PageIndex` Und`PageCount` auf den gewünschten Seitenbereich.

## Schritt 2: Speichern des Dokuments

 Abschließend können Sie das Dokument mit dem spezifischen Seitenbereich speichern`Save` Methode:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern des bearbeiteten Dokuments angeben.

Das ist alles ! Sie haben nun mit Aspose.Words für .NET einen bestimmten Seitenbereich aus einem PDF-Dokument geladen.

### Beispielquellcode für „Load Page Range Of Pdf“ mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Denken Sie daran, den korrekten Pfad zum Verzeichnis Ihrer PDF-Dokumente anzugeben.



