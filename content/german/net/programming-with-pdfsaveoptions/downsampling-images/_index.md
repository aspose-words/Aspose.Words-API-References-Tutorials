---
title: Reduzieren Sie die Größe von PDF-Dokumenten durch Downsampling von Bildern
linktitle: Reduzieren Sie die Größe von PDF-Dokumenten durch Downsampling von Bildern
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Größe von PDF-Dokumenten durch Downsampling von Bildern reduzieren, wenn Sie mit Aspose.Words für .NET in PDF konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/downsampling-images/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Reduzieren der PDF-Dokumentgröße durch Downsampling von Bildern bei der Konvertierung in PDF mit Aspose.Words für .NET. Dadurch wird die Größe der generierten PDF-Datei reduziert. Befolgen Sie die folgenden Schritte:

## Schritt 1: Dokument einlegen

Beginnen Sie mit dem Hochladen des Dokuments, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Achten Sie darauf, den richtigen Pfad zu Ihrem Dokument anzugeben.

## Schritt 2: PDF-Speicheroptionen konfigurieren

Erstellen Sie eine Instanz der Klasse PdfSaveOptions und legen Sie die Optionen zum Verkleinern des Bildes fest:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 Der`Resolution` Eigenschaft gibt die Zielauflösung der Bilder an und die`ResolutionThreshold`-Eigenschaft gibt die Mindestauflösung an, unter die die Bilder nicht verkleinert werden.

## Schritt 3: Dokument in PDF konvertieren

 Verwenden Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Speicheroptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode zum Downsampling von Bildern mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Wir können einen Mindestschwellenwert für das Downsampling festlegen.
	// Dieser Wert verhindert, dass das zweite Bild im Eingabedokument herunterskaliert wird.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Indem Sie diese Schritte befolgen, können Sie die Bildauflösung bei der Konvertierung in PDF mit Aspose.Words für .NET problemlos reduzieren.

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Größe eines PDF-Dokuments mit Bildabtastung reduzieren, wenn Sie es mit Aspose.Words für .NET in PDF konvertieren. Indem Sie die beschriebenen Schritte befolgen, können Sie die Auflösung von Bildern und die Größe der generierten PDF-Datei problemlos reduzieren. Geben Sie unbedingt den richtigen Pfad zu Ihrem Dokument an und konfigurieren Sie die Bildabtastungsoptionen nach Bedarf. Durch die Reduzierung der PDF-Dateigröße lässt sich die Datei einfacher teilen, speichern und schnell auf verschiedenen Plattformen laden. Profitieren Sie von den Vorteilen der Reduzierung der PDF-Dokumentgröße mit Bildabtastung mit Aspose.Words für .NET.

### Häufig gestellte Fragen

#### F: Was bedeutet die Reduzierung der Größe eines PDF-Dokuments durch Bildabtastung?
A: Durch die Reduzierung der PDF-Dokumentgröße mit Image Sampling wird die Größe der generierten PDF-Datei verringert, indem die Auflösung der Bilder bei der Konvertierung in PDF reduziert wird. Dies optimiert die Nutzung des Speicherplatzes und erleichtert das Teilen und Übertragen der PDF-Datei.

#### F: Wie kann ich die Größe eines PDF-Dokuments mithilfe von Bildsampling unter Verwendung von Aspose.Words für .NET reduzieren?
A: Um die Größe eines PDF-Dokuments mithilfe der Bildabtastung unter Verwendung von Aspose.Words für .NET zu reduzieren, befolgen Sie diese Schritte:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad Ihres Dokumentverzeichnisses.

 Laden Sie das Dokument, das Sie in PDF konvertieren möchten, mit dem`Document` Klasse und geben Sie den Pfad zum Dokument im angegebenen Dokumentverzeichnis an.

 Konfigurieren Sie die Optionen zum Speichern als PDF, indem Sie eine Instanz des`PdfSaveOptions` Klasse und Festlegen der Bildabtastoptionen mithilfe der`DownsampleOptions` Eigenschaft. Sie können die Zielauflösung von Bildern mit der`Resolution` Eigenschaft und legen Sie eine Mindestauflösung fest, oberhalb derer Bilder nicht mit der`ResolutionThreshold` Eigentum.

 Speichern Sie das Dokument im PDF-Format mit dem`Save` Methode der`Document` Klasse, die den Pfad und die Speicheroptionen angibt.

#### F: Welche Vorteile bietet die Reduzierung der PDF-Dokumentgröße durch Bildabtastung?
A: Die Reduzierung der PDF-Dokumentgröße durch Bildabtastung bietet folgende Vorteile:

Reduzierte PDF-Dateigröße: Durch die Bildabtastung wird die Auflösung der Bilder im PDF-Dokument reduziert, was zu einer deutlichen Reduzierung der PDF-Dateigröße führt. Dies erleichtert das Teilen und Übertragen der Datei, insbesondere per E-Mail oder online.

Optimierung des Speicherplatzes: Durch die Reduzierung der PDF-Dateigröße lässt sich der Speicherplatz optimal nutzen, insbesondere wenn Sie viele PDF-Dateien mit hochauflösenden Bildern haben.

Leistungsverbesserungen: Kleinere PDF-Dateien werden schneller geladen und können auf verschiedenen Geräten schneller geöffnet und angezeigt werden.