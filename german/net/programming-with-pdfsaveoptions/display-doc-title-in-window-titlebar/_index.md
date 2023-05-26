---
title: Dokumenttitel in der Titelleiste des Fensters anzeigen
linktitle: Dokumenttitel in der Titelleiste des Fensters anzeigen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie beim Konvertieren in PDF mit Aspose.Words für .NET den Dokumenttitel in der Titelleiste des Fensters anzeigen.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Anzeigen des Dokumenttitels in der Fenstertitelleiste mit Aspose.Words für .NET. Mit dieser Funktion können Sie den Dokumenttitel in der Titelleiste des Fensters anzeigen, wenn Sie das generierte PDF-Dokument öffnen. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments

Laden Sie zunächst das Dokument hoch, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokument angeben.

## Schritt 2: Konfigurieren Sie die PDF-Speicheroptionen

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und aktivieren Sie die Anzeige des Dokumenttitels in der Fenstertitelleiste:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Diese Option ermöglicht die Anzeige des Dokumenttitels in der Fenstertitelleiste beim Konvertieren in PDF.

## Schritt 3: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für die Anzeige des Dokumenttitels in der Fenstertitelleiste mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Anzeigen des Dokumenttitels in der Fenstertitelleiste in einem PDF-Dokument mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
Wenn Sie diese Schritte befolgen, können Sie den Dokumenttitel beim Konvertieren in PDF mit Aspose.Words für .NET ganz einfach in der Titelleiste des Fensters anzeigen.

