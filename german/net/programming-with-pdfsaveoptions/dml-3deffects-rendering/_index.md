---
title: Dml 3DEffects Rendering
linktitle: Dml 3DEffects Rendering
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie das Rendern von 3D-DML-Effekten bei der Konvertierung in PDF mit Aspose.Words für .NET aktivieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Aktivieren des 3D-DML-Effekt-Renderings bei der Konvertierung in PDF mit Aspose.Words für .NET. Dadurch bleiben die 3D-Effekte im generierten PDF-Dokument erhalten. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments

Laden Sie zunächst das Dokument hoch, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokument angeben.

## Schritt 2: PDF-Speicheroptionen konfigurieren

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und aktivieren Sie das erweiterte Rendering von 3D-DML-Effekten:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Diese Option behält die 3D-Effekte im generierten PDF-Dokument bei.

## Schritt 3: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Speicheroptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für Dml 3DEffects Rendering mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Wenn Sie diese Schritte befolgen, können Sie das Rendern von 3D-DML-Effekten bei der Konvertierung in PDF mit Aspose.Words für .NET ganz einfach aktivieren.



