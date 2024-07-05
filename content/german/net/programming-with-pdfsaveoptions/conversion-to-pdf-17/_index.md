---
title: Word-Dokument in PDF konvertieren 1.7
linktitle: Word-Dokument in PDF konvertieren 1.7
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Word-Dokumente in PDF 1.7 konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Konvertieren von Word-Dokumenten in PDF 1.7 mit Aspose.Words für .NET. Durch die Konvertierung in PDF 1.7 können Sie PDF-Dateien erstellen, die dem PDF 1.7-Standard entsprechen. Befolgen Sie die folgenden Schritte:

## Schritt 1: Dokument einlegen

Beginnen Sie mit dem Hochladen des Dokuments, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Achten Sie darauf, den richtigen Pfad zu Ihrem Dokument anzugeben.

## Schritt 2: PDF-Konvertierungsoptionen festlegen

Erstellen Sie eine Instanz der Klasse PdfSaveOptions und geben Sie die Version des PDF-Standards an, die Sie verwenden möchten:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Diese Option stellt sicher, dass die generierte PDF-Datei dem PDF 1.7-Standard entspricht.

## Schritt 3: Dokument in PDF konvertieren

 Verwenden Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispiel-Quellcode für die Konvertierung in PDF 17 mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zur Konvertierung in PDF 1.7 mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET problemlos in PDF 1.7 konvertieren.


## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie ein Word-Dokument mit Aspose.Words für .NET in PDF 1.7 konvertieren. Indem Sie die beschriebenen Schritte befolgen, können Sie ganz einfach PDF-Dateien erstellen, die dem PDF 1.7-Standard entsprechen. Geben Sie unbedingt den richtigen Pfad zu Ihrem Word-Dokument an und konfigurieren Sie die Optionen für die Konvertierung in PDF nach Bedarf. Die Konvertierung in PDF 1.7 gewährleistet optimale Kompatibilität und Lesbarkeit auf verschiedenen Plattformen.

### Häufig gestellte Fragen

#### F: Was ist die Konvertierung von Word in PDF 1.7?
A: Durch die Konvertierung von Word-Dokumenten in PDF 1.7 werden PDF-Dateien erstellt, die dem PDF 1.7-Standard entsprechen. Dieser Standard legt Funktionen und Anforderungen für PDF-Dateien fest und sorgt so für optimale Kompatibilität und Lesbarkeit auf verschiedenen Plattformen.

#### F: Wie kann ich mit Aspose.Words für .NET ein Word-Dokument in PDF 1.7 konvertieren?
A: Um ein Word-Dokument mit Aspose.Words für .NET in PDF 1.7 zu konvertieren, folgen Sie diesen Schritten:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad Ihres Dokumentverzeichnisses.

 Laden Sie das Word-Dokument, das Sie in PDF konvertieren möchten, mit dem`Document` Klasse und geben Sie den Pfad zum Word-Dokument im angegebenen Dokumentverzeichnis an.

 Konfigurieren Sie die Konvertierung als PDF-Optionen, indem Sie eine Instanz des`PdfSaveOptions`Klasse und geben Sie die Version des PDF-Standards an, den Sie verwenden möchten, mithilfe der`Compliance` Eigenschaft mit dem Wert`PdfCompliance. Pdf17` um eine PDF-Datei zu erzeugen, die dem PDF 1.7-Standard entspricht.

 Speichern Sie das Dokument im PDF-Format mit dem`Save` Methode der`Document` Klasse, die den Pfad und die Speicheroptionen angibt.

#### F: Welche Vorteile bietet die Konvertierung in PDF 1.7 mit Aspose.Words für .NET?
A: Die Vorteile der Konvertierung in PDF 1.7 mit Aspose.Words für .NET sind:

PDF 1.7-kompatibel: Durch die Konvertierung in PDF 1.7 wird sichergestellt, dass die generierte PDF-Datei PDF 1.7-kompatibel ist, wodurch Kompatibilität und Lesbarkeit auf verschiedenen Plattformen gewährleistet werden.

Beibehaltung der Dokumentformatierung: Aspose.Words für .NET gewährleistet eine genaue Konvertierung von Word-Dokumenten durch Beibehaltung von Formatierungen, Bildern und Stilen, was zu einer originalgetreuen PDF-Datei führt.