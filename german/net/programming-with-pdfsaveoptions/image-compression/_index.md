---
title: Bildkompression
linktitle: Bildkompression
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Komprimierung von Bildern mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/image-compression/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Bildkomprimierungsfunktion mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie Bilder in einem Dokument komprimieren und eine PDF-Datei mit der richtigen Bildkomprimierung erstellen.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Rendering.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF mit Bildkomprimierung

 Um Bilder beim Konvertieren in PDF zu komprimieren, müssen wir das konfigurieren`PdfSaveOptions` Objekt. Bei Bedarf können wir den Bildkomprimierungstyp, die JPEG-Qualität und andere PDF-Konformitätsoptionen festlegen.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Schritt 4: Dokument als PDF mit Bildkomprimierung speichern

Schließlich können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Schritt 5: Konfigurieren Sie Optionen zum Speichern in PDF/A-2u mit Bildkomprimierung

Wenn Sie PDF/A-2u-konforme PDFs mit Bildkomprimierung erstellen möchten, können Sie die zusätzlichen Speicheroptionen konfigurieren.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Verwenden Sie die JPEG-Komprimierung mit 50 % Qualität, um die Dateigröße zu reduzieren.
};
```

## Schritt 6: Speichern Sie das Dokument als PDF/A-2u mit Bildkomprimierung

Speichern Sie das Dokument im PDF/A-2u-Format mit den zuvor konfigurierten zusätzlichen Speicheroptionen.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Das ist alles ! Sie haben die Bilder in einem Dokument erfolgreich komprimiert und mit Aspose.Words für .NET eine PDF-Datei mit ordnungsgemäßer Bildkomprimierung generiert.

### Beispielquellcode zum Komprimieren von Bildern mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Verwenden Sie die JPEG-Komprimierung mit 50 % Qualität, um die Dateigröße zu reduzieren.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```
