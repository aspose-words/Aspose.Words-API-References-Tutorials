---
title: Reduzieren Sie die Größe von PDF-Dokumenten durch Downsampling von Bildern
linktitle: Reduzieren Sie die Größe von PDF-Dokumenten durch Downsampling von Bildern
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Größe von PDF-Dokumenten durch Downsampling von Bildern bei der Konvertierung in PDF mit Aspose.Words für .NET reduzieren können.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/downsampling-images/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Reduzieren der PDF-Dokumentgröße durch Downsampling von Bildern bei der Konvertierung in PDF mit Aspose.Words für .NET. Dadurch wird die Größe der generierten PDF-Datei reduziert. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments

Laden Sie zunächst das Dokument hoch, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokument angeben.

## Schritt 2: PDF-Speicheroptionen konfigurieren

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und legen Sie die Bildverkleinerungsoptionen fest:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 Der`Resolution` Die Eigenschaft gibt die Zielauflösung der Bilder und der an`ResolutionThreshold`Die Eigenschaft gibt die Mindestauflösung an, unter der die Bilder nicht verkleinert werden.

## Schritt 3: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Speicheroptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für das Downsampling von Bildern mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Wir können einen Mindestschwellenwert für das Downsampling festlegen.
	// Dieser Wert verhindert, dass das zweite Bild im Eingabedokument heruntergerechnet wird.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Wenn Sie diese Schritte befolgen, können Sie die Bildauflösung beim Konvertieren in PDF mit Aspose.Words für .NET ganz einfach reduzieren.

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Größe eines PDF-Dokuments durch Bildsampling bei der Konvertierung in PDF mit Aspose.Words für .NET reduzieren können. Durch Befolgen der beschriebenen Schritte können Sie die Auflösung von Bildern und die Größe der generierten PDF-Datei ganz einfach reduzieren. Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokument angeben und die Bild-Sampling-Optionen nach Bedarf konfigurieren. Die Reduzierung der PDF-Dateigröße erleichtert das Teilen, Speichern und schnelle Laden der Datei auf verschiedenen Plattformen. Genießen Sie die Vorteile der Reduzierung der PDF-Dokumentgröße durch Bild-Sampling mit Aspose.Words für .NET.

### Häufig gestellte Fragen

#### F: Was bedeutet die Reduzierung der Größe des PDF-Dokuments durch Bild-Sampling?
A: Durch die Reduzierung der PDF-Dokumentgröße mit Image Sampling wird die Größe der generierten PDF-Datei verringert, indem die Auflösung der Bilder bei der Konvertierung in PDF verringert wird. Dies optimiert die Nutzung des Speicherplatzes und erleichtert das Teilen und Übertragen der PDF-Datei.

#### F: Wie kann ich die Größe eines PDF-Dokuments durch Bildstichproben mit Aspose.Words für .NET reduzieren?
A: Um die Größe eines PDF-Dokuments durch Bild-Sampling mit Aspose.Words für .NET zu reduzieren, führen Sie die folgenden Schritte aus:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad Ihres Dokumentenverzeichnisses.

 Laden Sie das Dokument, das Sie in PDF konvertieren möchten, mit`Document` Klasse und geben Sie den Pfad zum Dokument im angegebenen Dokumentenverzeichnis an.

 Konfigurieren Sie die Optionen zum Speichern als PDF, indem Sie eine Instanz davon erstellen`PdfSaveOptions` Klasse und Festlegen der Bild-Sampling-Optionen mithilfe der`DownsampleOptions` Eigentum. Sie können die Zielauflösung von Bildern mit festlegen`Resolution` -Eigenschaft und legen Sie einen Mindestauflösungsschwellenwert fest, oberhalb dessen Bilder nicht mit der verkleinert werden`ResolutionThreshold` Eigentum.

 Speichern Sie das Dokument im PDF-Format mit`Save` Methode der`Document` Klasse, die den Pfad und die Speicheroptionen angibt.

#### F: Welche Vorteile bietet die Reduzierung der PDF-Dokumentgröße durch Bildstichproben?
A: Die Reduzierung der PDF-Dokumentgröße durch Bild-Sampling bietet folgende Vorteile:

Reduzierte PDF-Dateigröße: Durch Bildsampling wird die Auflösung der Bilder im PDF-Dokument verringert, was zu einer erheblichen Verringerung der PDF-Dateigröße führt. Dies erleichtert das Teilen und Übertragen der Datei, insbesondere per E-Mail oder online.

Optimierung des Speicherplatzes: Durch die Reduzierung der Größe der PDF-Datei können Sie die Nutzung des Speicherplatzes optimieren, insbesondere wenn Sie viele PDF-Dateien mit hochauflösenden Bildern haben.

Leistungsverbesserungen: Kleinere PDF-Dateien werden schneller geladen und können auf verschiedenen Geräten schneller geöffnet und angezeigt werden.