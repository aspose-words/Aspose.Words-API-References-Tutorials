---
title: Skalieren Sie WMF-Schriftarten auf Metadateigröße
linktitle: Skalieren Sie WMF-Schriftarten auf Metadateigröße
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Anpassen der WMF-Schriftgröße beim Konvertieren in PDF mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der WMF-Funktion „Schriftskalierung auf Metadateigröße“ mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie die WMF-Schriftskalierung beim Konvertieren in PDF aktivieren oder deaktivieren.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „WMF with text.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Schritt 3: Konfigurieren Sie die Metadatei-Rendering-Optionen

 Um die WMF-Schriftskalierung auf die Metadateigröße zu aktivieren oder zu deaktivieren, müssen wir Folgendes konfigurieren`MetafileRenderingOptions` Objekt. In diesem Beispiel deaktivieren wir die Schriftskalierung, indem wir die festlegen`ScaleWmfFontsToMetafileSize` Eigentum zu`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Schritt 4: Konfigurieren Sie die Optionen zum Speichern als PDF mit Metadatei-Rendering-Optionen

Schließlich können wir die Optionen zum Speichern in PDF mithilfe der zuvor konfigurierten Metadatei-Rendering-Optionen konfigurieren.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Schritt 5: Speichern Sie das Dokument als PDF mit Metadatei-Rendering-Optionen

Speichern Sie das Dokument im PDF-Format mit den zuvor konfigurierten Speicheroptionen.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Das ist alles ! Sie haben die Skalierung der WMF-Schriftarten auf die Metadateigröße beim Konvertieren erfolgreich aktiviert oder deaktiviert

ein PDF-Dokument mit Aspose.Words für .NET.

### Beispielquellcode zum Skalieren von WMF-Schriftarten auf Metadateigröße mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Wenn Aspose.Words einige der Metadateidatensätze nicht korrekt in Vektorgrafiken rendern kann
	// dann rendert Aspose.Words diese Metadatei in eine Bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```
