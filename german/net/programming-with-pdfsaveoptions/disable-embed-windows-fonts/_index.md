---
title: Deaktivieren Sie das Einbetten von Windows-Schriftarten
linktitle: Deaktivieren Sie das Einbetten von Windows-Schriftarten
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Einbettung von Windows-Schriftarten deaktivieren, wenn Sie Dokumente mit Aspose.Words für .NET in PDF konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Deaktivieren der Einbettung von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET. Durch Deaktivieren der Schriftarteinbettung können Sie die Größe der generierten PDF-Datei reduzieren. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments

Laden Sie zunächst das Dokument hoch, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokument angeben.

## Schritt 2: PDF-Speicheroptionen festlegen

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und geben Sie an, wie Schriftarten eingebettet werden sollen:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Mit dieser Option können Sie die Integration von Windows-Schriftarten in der generierten PDF-Datei deaktivieren.

## Schritt 3: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für die Deaktivierung der Einbettung von Windows-Schriftarten mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Deaktivieren der Einbettung von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Das Ausgabe-PDF wird ohne Einbettung von Standard-Windows-Schriftarten gespeichert.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Wenn Sie diese Schritte befolgen, können Sie die Einbettung von Windows-Schriftarten in ein PDF-Dokument mit Aspose.Words für .NET ganz einfach deaktivieren.

