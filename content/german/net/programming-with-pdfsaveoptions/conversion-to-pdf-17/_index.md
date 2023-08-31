---
title: Word-Dokument in PDF konvertieren 1.7
linktitle: Word-Dokument in PDF konvertieren 1.7
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Word-Dokumente mit Aspose.Words für .NET in PDF 1.7 konvertieren.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

In diesem Tutorial führen wir Sie durch die Schritte zum Konvertieren eines Word-Dokuments in PDF 1.7 mit Aspose.Words für .NET. Durch die Konvertierung in PDF 1.7 können Sie PDF-Dateien generieren, die dem PDF 1.7-Standard entsprechen. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments

Laden Sie zunächst das Dokument hoch, das Sie in PDF konvertieren möchten:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokument angeben.

## Schritt 2: PDF-Konvertierungsoptionen festlegen

Erstellen Sie eine Instanz der PdfSaveOptions-Klasse und geben Sie die Version des PDF-Standards an, die Sie verwenden möchten:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Diese Option stellt sicher, dass die generierte PDF-Datei dem PDF 1.7-Standard entspricht.

## Schritt 3: Dokument in PDF konvertieren

 Benutzen Sie die`Save` Methode zum Konvertieren des Dokuments in PDF unter Angabe der Konvertierungsoptionen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Speichern der konvertierten PDF-Datei angeben.

### Beispielquellcode für die Konvertierung in PDF 17 mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Konvertieren in PDF 1.7 mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach in PDF 1.7 konvertieren.


## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie mit Aspose.Words für .NET ein Word-Dokument in PDF 1.7 konvertieren. Wenn Sie die beschriebenen Schritte befolgen, können Sie ganz einfach PDF-Dateien generieren, die dem PDF 1.7-Standard entsprechen. Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Word-Dokument angeben und die Optionen für die Konvertierung in PDF nach Bedarf konfigurieren. Die Konvertierung nach PDF 1.7 sorgt für optimale Kompatibilität und Lesbarkeit auf verschiedenen Plattformen.

### Häufig gestellte Fragen

#### F: Was ist die Konvertierung von Word in PDF 1.7?
A: Beim Konvertieren von Word-Dokumenten in PDF 1.7 werden PDF-Dateien generiert, die dem PDF 1.7-Standard entsprechen. Dieser Standard legt Funktionen und Anforderungen für PDF-Dateien fest und ermöglicht so optimale Kompatibilität und Lesbarkeit auf verschiedenen Plattformen.

#### F: Wie kann ich mit Aspose.Words für .NET ein Word-Dokument in PDF 1.7 konvertieren?
A: Um ein Word-Dokument mit Aspose.Words für .NET in PDF 1.7 zu konvertieren, gehen Sie folgendermaßen vor:

 Legen Sie den Verzeichnispfad fest, in dem sich Ihre Dokumente befinden, indem Sie ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad Ihres Dokumentenverzeichnisses.

 Laden Sie das Word-Dokument, das Sie in PDF konvertieren möchten, mit`Document` Klasse und geben Sie den Pfad zum Word-Dokument im angegebenen Dokumentenverzeichnis an.

 Konfigurieren Sie die Konvertierungsoptionen als PDF, indem Sie eine Instanz davon erstellen`PdfSaveOptions`Klasse und geben Sie die Version des PDF-Standards an, den Sie verwenden möchten`Compliance` Eigenschaft mit dem Wert`PdfCompliance. Pdf17` um eine PDF-Datei zu generieren, die dem PDF 1.7-Standard entspricht.

 Speichern Sie das Dokument im PDF-Format mit`Save` Methode der`Document`Klasse, die den Pfad und die Speicheroptionen angibt.

#### F: Welche Vorteile bietet die Konvertierung in PDF 1.7 mit Aspose.Words für .NET?
A: Die Vorteile der Konvertierung in PDF 1.7 mit Aspose.Words für .NET sind:

PDF 1.7-kompatibel: Durch die Konvertierung in PDF 1.7 wird sichergestellt, dass die generierte PDF-Datei PDF 1.7-kompatibel ist und somit Kompatibilität und Lesbarkeit auf verschiedenen Plattformen gewährleistet ist.

Beibehaltung der Dokumentformatierung: Aspose.Words für .NET gewährleistet eine genaue Konvertierung von Word-Dokumenten durch Beibehaltung von Formatierungen, Bildern und Stilen, was zu einer originalgetreuen PDF-Datei führt.