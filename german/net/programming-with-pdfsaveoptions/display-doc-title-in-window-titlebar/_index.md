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

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Dokumenttitel in Fenstertitelleiste anzeigen“ mit Aspose.Words für .NET?
Mit der Funktion „Dokumenttitel in Fenstertitelleiste anzeigen“ von Aspose.Words für .NET können Sie den Dokumenttitel in der Fenstertitelleiste anzeigen, wenn Sie das generierte PDF-Dokument öffnen. Dies erleichtert die Identifizierung und Unterscheidung von PDF-Dokumenten in Ihrer Leseumgebung.

#### F: Wie kann ich diese Funktion mit Aspose.Words für .NET verwenden?
Um diese Funktion mit Aspose.Words für .NET zu verwenden, führen Sie die folgenden Schritte aus:

 Laden Sie das Dokument mit`Document` -Methode und Angabe des Pfads der Datei, die in PDF konvertiert werden soll.

 Konfigurieren Sie PDF-Speicheroptionen, indem Sie eine Instanz davon erstellen`PdfSaveOptions` Klasse und Einstellung der`DisplayDocTitle` Eigentum zu`true`. Dies ermöglicht die Anzeige des Dokumenttitels in der Fenstertitelleiste beim Konvertieren in PDF.

 Benutzen Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen.

#### F: Ändert diese Funktion den Inhalt des Dokuments selbst?
Nein, diese Funktion verändert nicht den Inhalt des Dokuments selbst. Es wirkt sich nur auf die Anzeige des Dokumenttitels in der Titelleiste des Fensters aus, wenn es als PDF-Dokument geöffnet wird. Der Inhalt des Dokuments bleibt unverändert.

#### F: Ist es möglich, den Titel des Dokuments anzupassen, der in der Titelleiste des Fensters angezeigt wird?
 Ja, Sie können den in der Titelleiste des Fensters angezeigten Dokumenttitel anpassen, indem Sie ändern`Document.Title` Eigenschaft des Dokuments, bevor Sie es in PDF konvertieren. Über eine Zeichenfolge können Sie den gewünschten Titel festlegen. Stellen Sie sicher, dass Sie den Titel festlegen, bevor Sie anrufen`Save` Methode zum Konvertieren in PDF.

#### F: Welche anderen Ausgabeformate unterstützt Aspose.Words für die Dokumentkonvertierung?
Aspose.Words für .NET unterstützt viele Ausgabeformate für die Dokumentkonvertierung, wie z. B. PDF, XPS, HTML, EPUB, MOBI, Bilder (JPEG, PNG, BMP, TIFF, GIF) und viele mehr. wieder andere. Sie können das passende Ausgabeformat entsprechend Ihren spezifischen Anforderungen auswählen.