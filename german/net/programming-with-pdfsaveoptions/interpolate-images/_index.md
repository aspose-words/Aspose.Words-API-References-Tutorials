---
title: Bilder interpolieren
linktitle: Bilder interpolieren
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Aktivieren der Bildinterpolation mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/interpolate-images/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Bildinterpolationsfunktion mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie die Bildinterpolation beim Konvertieren in PDF aktivieren.

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

## Schritt 3: Konfigurieren Sie Optionen zum Speichern als PDF mit Frame-Interpolation

 Um die Interpolation von Bildern beim Konvertieren in PDF zu ermöglichen, müssen wir das konfigurieren`PdfSaveOptions` Objekt durch Festlegen des`InterpolateImages` Eigentum zu`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };
```

## Schritt 4: Speichern Sie das Dokument als PDF mit Frame-Interpolation

Schließlich können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);
```

Das ist alles ! Sie haben die Bildinterpolation beim Konvertieren eines Dokuments in PDF mit Aspose.Words für .NET erfolgreich aktiviert.

### Beispielquellcode für die Bildinterpolation mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);

```
