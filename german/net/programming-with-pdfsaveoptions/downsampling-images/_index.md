---
title: Downsampling von Bildern
linktitle: Downsampling von Bildern
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Bildauflösung beim Konvertieren in PDF mit Aspose.Words für .NET reduzieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/downsampling-images/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Reduzierung der Bildauflösung beim Konvertieren in PDF mit Aspose.Words für .NET. Dadurch wird die Größe der generierten PDF-Datei reduziert. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments

Laden Sie zunächst das Dokument hoch, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokument angeben.

## Schritt 2: PDF-Speicheroptionen konfigurieren

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und legen Sie die Bildverkleinerungsoptionen fest:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 Der`Resolution` Die Eigenschaft gibt die Zielauflösung der Bilder und der an`ResolutionThreshold` Die Eigenschaft gibt die Mindestauflösung an, unter der die Bilder nicht verkleinert werden.

## Schritt 3: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Speicheroptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für das Downsampling von Bildern mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//Wir können einen Mindestschwellenwert für das Downsampling festlegen.
	// Dieser Wert verhindert, dass das zweite Bild im Eingabedokument heruntergerechnet wird.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Wenn Sie diese Schritte befolgen, können Sie die Bildauflösung beim Konvertieren in PDF mit Aspose.Words für .NET ganz einfach reduzieren.


