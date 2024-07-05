---
title: Dokumenttitel in der Fenstertitelleiste anzeigen
linktitle: Dokumenttitel in der Fenstertitelleiste anzeigen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie beim Konvertieren in PDF mit Aspose.Words für .NET den Dokumenttitel in der Fenstertitelleiste anzeigen.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Anzeigen des Dokumenttitels in der Fenstertitelleiste mit Aspose.Words für .NET. Mit dieser Funktion können Sie den Dokumenttitel in der Fenstertitelleiste anzeigen, wenn Sie das generierte PDF-Dokument öffnen. Befolgen Sie die folgenden Schritte:

## Schritt 1: Dokument einlegen

Beginnen Sie mit dem Hochladen des Dokuments, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Achten Sie darauf, den richtigen Pfad zu Ihrem Dokument anzugeben.

## Schritt 2: PDF-Speicheroptionen konfigurieren

Erstellen Sie eine Instanz der Klasse PdfSaveOptions und aktivieren Sie die Anzeige des Dokumenttitels in der Fenstertitelleiste:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Diese Option aktiviert die Anzeige des Dokumenttitels in der Fenstertitelleiste bei der Konvertierung in PDF.

## Schritt 3: Dokument in PDF konvertieren

 Verwenden Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für „Dokumenttitel in Fenstertitelleiste anzeigen“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Anzeigen des Dokumenttitels in der Fenstertitelleiste in einem PDF-Dokument mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
Wenn Sie diese Schritte befolgen, können Sie den Dokumenttitel bei der Konvertierung in PDF mit Aspose.Words für .NET problemlos in der Titelleiste des Fensters anzeigen.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Dokumenttitel in der Fenstertitelleiste anzeigen“ mit Aspose.Words für .NET?
Mit der Funktion „Dokumenttitel in Fenstertitelleiste anzeigen“ von Aspose.Words für .NET können Sie den Dokumenttitel in der Fenstertitelleiste anzeigen, wenn Sie das generierte PDF-Dokument öffnen. Dies erleichtert das Identifizieren und Unterscheiden von PDF-Dokumenten in Ihrer Leseumgebung.

#### F: Wie kann ich diese Funktion mit Aspose.Words für .NET verwenden?
Um diese Funktion mit Aspose.Words für .NET zu verwenden, gehen Sie folgendermaßen vor:

 Laden Sie das Dokument mit dem`Document` Methode und geben Sie den Pfad der in PDF zu konvertierenden Datei an.

 Konfigurieren Sie PDF-Speicheroptionen, indem Sie eine Instanz des`PdfSaveOptions` Klasse und Festlegen der`DisplayDocTitle`Eigentum an`true`. Dies ermöglicht die Anzeige des Dokumenttitels in der Fenstertitelleiste bei der Konvertierung in PDF.

 Verwenden Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen.

#### F: Ändert diese Funktion den Inhalt des Dokuments selbst?
Nein, diese Funktion verändert nicht den Inhalt des Dokuments selbst. Sie wirkt sich lediglich auf die Anzeige des Dokumenttitels in der Fenstertitelleiste aus, wenn das Dokument als PDF-Dokument geöffnet wird. Der Inhalt des Dokuments bleibt unverändert.

#### F: Ist es möglich, den Titel des Dokuments anzupassen, der in der Titelleiste des Fensters angezeigt wird?
 Ja, Sie können den in der Titelleiste des Fensters angezeigten Dokumenttitel anpassen, indem Sie den`Document.Title` Eigenschaft des Dokuments, bevor Sie es in PDF konvertieren. Sie können den gewünschten Titel mithilfe einer Zeichenfolge festlegen. Stellen Sie sicher, dass Sie den Titel festlegen, bevor Sie den`Save` Methode zur Konvertierung in PDF.

#### F: Welche anderen Ausgabeformate unterstützt Aspose.Words für die Dokumentkonvertierung?
Aspose.Words für .NET unterstützt viele Ausgabeformate für die Dokumentkonvertierung, wie PDF, XPS, HTML, EPUB, MOBI, Bild (JPEG, PNG, BMP, TIFF, GIF) und viele mehr. Sie können das entsprechende Ausgabeformat entsprechend Ihren spezifischen Anforderungen auswählen.