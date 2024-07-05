---
title: Rendern Sie 3D-DML-3DEffects in einem PDF-Dokument
linktitle: Rendern Sie 3D-DML-3DEffects in einem PDF-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie das Rendern von 3D-DML-Effekten bei der Konvertierung in PDF mit Aspose.Words für .NET aktivieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Aktivieren der 3D-DML-Effektdarstellung bei der Konvertierung in PDF mit Aspose.Words für .NET. Dadurch bleiben die 3D-Effekte im generierten PDF-Dokument erhalten. Befolgen Sie die folgenden Schritte:

## Schritt 1: Dokument einlegen

Beginnen Sie mit dem Hochladen des Dokuments, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Achten Sie darauf, den richtigen Pfad zu Ihrem Dokument anzugeben.

## Schritt 2: PDF-Speicheroptionen konfigurieren

Erstellen Sie eine Instanz der Klasse PdfSaveOptions und aktivieren Sie die erweiterte Darstellung von 3D-DML-Effekten:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Diese Option behält die 3D-Effekte im generierten PDF-Dokument bei.

## Schritt 3: Dokument in PDF konvertieren

 Verwenden Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Speicheroptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispiel-Quellcode für Dml 3DEffects Rendering mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Indem Sie diese Schritte befolgen, können Sie das Rendern von 3D-DML-Effekten bei der Konvertierung in PDF mit Aspose.Words für .NET problemlos aktivieren.

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie das Rendern von 3D-DML-Effekten beim Konvertieren in PDF mit Aspose.Words für .NET aktivieren. Indem Sie die beschriebenen Schritte befolgen, können Sie die 3D-Effekte im generierten PDF-Dokument problemlos beibehalten. Verwenden Sie diese Funktion, um die wichtigen visuellen Effekte Ihres Originaldokuments beizubehalten.


### Häufig gestellte Fragen

#### F: Was ist das Rendern von 3D-DML-Effekten in einem PDF-Dokument?
A: Das Rendern von 3D-DML-Effekten in einem PDF-Dokument bezieht sich auf die Möglichkeit, 3D-Effekte bei der Konvertierung eines Dokuments in das PDF-Format beizubehalten. Dadurch bleiben die visuellen Effekte erhalten und es wird sichergestellt, dass das generierte PDF-Dokument wie das Originaldokument aussieht.

#### F: Wie kann ich das Rendern von 3D-DML-Effekten beim Konvertieren in PDF mit Aspose.Words für .NET aktivieren?
A: Um das Rendern von 3D-DML-Effekten bei der Konvertierung in PDF mit Aspose.Words für .NET zu aktivieren, befolgen Sie diese Schritte:

 Erstellen Sie eine Instanz des`Document` Klasse, die den Pfad zum Word-Dokument angibt.

 Erstellen Sie eine Instanz des`PdfSaveOptions` Klasse und legen Sie die`Dml3DEffectsRenderingMode`Eigentum an`Dml3DEffectsRenderingMode.Advanced` um das erweiterte Rendern von 3D-DML-Effekten zu ermöglichen.

 Verwenden Sie die`Save` Methode der`Document`Klasse, um das Dokument durch Angabe von Speicheroptionen im PDF-Format zu speichern.

#### F: Wie kann ich überprüfen, ob im generierten PDF-Dokument 3D-DML-Effekte gerendert wurden?
A: Um zu prüfen, ob die 3D-DML-Effekte im generierten PDF-Dokument gerendert wurden, öffnen Sie die PDF-Datei mit einem kompatiblen PDF-Viewer wie Adobe Acrobat Reader und untersuchen Sie das Dokument. Sie sollten die 3D-Effekte so sehen, wie sie im Originaldokument erscheinen.



