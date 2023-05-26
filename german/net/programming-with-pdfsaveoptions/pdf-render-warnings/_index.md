---
title: PDF-Renderwarnungen
linktitle: PDF-Renderwarnungen
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Umgang mit PDF-Rendering-Warnungen mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der PDF-Rendering-Warnungsfunktion mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie beim Konvertieren in PDF mit Rendering-Warnungen umgehen.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „WMF with image.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF mit Rendering-Warnungen

Um Rendering-Warnungen beim Konvertieren in PDF zu verarbeiten, müssen wir Folgendes konfigurieren`MetafileRenderingOptions` -Objekt, um anzugeben, wie Metadateien gerendert werden. Wir nutzen auch die`HandleDocumentWarnings` Option zum Behandeln der Warnungen, die beim Speichern des Dokuments generiert werden.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## Schritt 4: Dokument als PDF mit Rendering-Warnungen speichern

Schließlich können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## Schritt 5: Behandeln Sie Rendering-Warnungen

Beim Speichern des Dokuments generierte Rendering-Warnungen können mit dem benutzerdefinierten Warnungshandler abgerufen werden. In diesem Beispiel drucken wir einfach die Beschreibung jeder Warnung aus.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

Das ist alles ! Sie haben die Rendering-Warnungen beim Konvertieren eines Dokuments erfolgreich behoben

  in PDF mit Aspose.Words für .NET.

### Beispielquellcode für PDF-Rendering-Warnungen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	// Wenn Aspose.Words einige der Metadateidatensätze nicht korrekt rendern kann
	// in Vektorgrafiken umwandelt, rendert Aspose.Words diese Metadatei in eine Bitmap.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// Während die Datei erfolgreich gespeichert wird, werden hier Rendering-Warnungen gesammelt, die während des Speicherns aufgetreten sind.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```
