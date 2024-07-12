---
title: Seitenbereich einer PDF laden
linktitle: Seitenbereich einer PDF laden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Laden eines bestimmten PDF-Seitenbereichs mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET einen bestimmten Seitenbereich aus einem PDF-Dokument laden. Folgen Sie den folgenden Schritten:

## Schritt 1: Einen Bereich von PDF-Seiten laden

Um einen bestimmten Seitenbereich aus einem PDF-Dokument zu laden, verwenden Sie folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 In diesem Beispiel laden wir die erste Seite des PDF-Dokuments. Sie können die Werte von`PageIndex`Und`PageCount` auf den gewünschten Seitenbereich.

## Schritt 2: Speichern des Dokuments

 Abschließend können Sie das Dokument mit dem Seitenbereich speichern, indem Sie`Save` Methode:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Geben Sie unbedingt den richtigen Pfad zum Speichern des bearbeiteten Dokuments an.

Das ist alles! Sie haben jetzt mit Aspose.Words für .NET einen bestimmten Seitenbereich aus einem PDF-Dokument geladen.

### Beispielquellcode zum Laden des Seitenbereichs einer PDF mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Denken Sie daran, den richtigen Pfad zum Verzeichnis Ihrer PDF-Dokumente anzugeben.



