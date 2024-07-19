---
title: Bildkomprimierung in einem PDF-Dokument
linktitle: Bildkomprimierung in einem PDF-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Komprimieren von Bildern in einem PDF-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/image-compression/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion „Bildkomprimierung in einem PDF-Dokument“ mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie Bilder in einem Dokument komprimieren und ein PDF mit der richtigen Bildkomprimierung erstellen.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Dokumentverzeichnis festlegen

 Zunächst müssen Sie den Pfad zum Verzeichnis angeben, in dem sich Ihre Dokumente befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Dokument hochladen

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Rendering.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF mit Bildkomprimierung

 Um Bilder bei der Konvertierung in PDF zu komprimieren, müssen wir die`PdfSaveOptions` Objekt. Wir können bei Bedarf Bildkomprimierungstyp, JPEG-Qualität und andere PDF-Kompatibilitätsoptionen festlegen.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Schritt 4: Dokument als PDF mit Bildkomprimierung speichern

Abschließend können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Schritt 5: Konfigurieren Sie die Optionen zum Speichern im PDF/A-2u-Format mit Bildkomprimierung

Wenn Sie ein PDF/A-2u-kompatibles PDF mit Bildkomprimierung erstellen möchten, können Sie die zusätzlichen Speicheroptionen konfigurieren.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Verwenden Sie JPEG-Komprimierung mit 50 % Qualität, um die Dateigröße zu reduzieren.
};
```

## Schritt 6: Speichern Sie das Dokument als PDF/A-2u mit Bildkomprimierung

Speichern Sie das Dokument im PDF/A-2u-Format mit den zuvor konfigurierten zusätzlichen Speicheroptionen.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Das ist alles! Sie haben die Bilder in einem Dokument erfolgreich komprimiert und mit Aspose.Words für .NET ein PDF mit der richtigen Bildkomprimierung erstellt.

### Beispiel-Quellcode zum Komprimieren von Bildern mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Verwenden Sie JPEG-Komprimierung bei 50 % Qualität, um die Dateigröße zu reduzieren.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie Bilder in einem PDF-Dokument mit Aspose.Words für .NET komprimieren. Indem Sie die beschriebenen Schritte befolgen, können Sie die Größe der Bilder in Ihrem PDF-Dokument problemlos reduzieren und ein PDF mit der richtigen Bildkomprimierung erstellen. Verwenden Sie die Bildkomprimierungsfunktionen von Aspose.Words für .NET, um die Größe Ihrer PDF-Dokumente zu optimieren und gleichzeitig die Bildqualität beizubehalten.

### Häufig gestellte Fragen

#### F: Was ist Bildkomprimierung in einem PDF-Dokument?
A: Durch das Komprimieren von Bildern in einem PDF-Dokument wird die Größe der im PDF-Dokument enthaltenen Bilder reduziert, um die Gesamtgröße der PDF-Datei zu verringern. Dadurch wird weniger Speicherplatz benötigt und die Leistung beim Laden und Anzeigen der PDF-Datei verbessert.

#### F: Wie kann ich mit Aspose.Words für .NET Bilder in einem PDF-Dokument komprimieren?
A: Um Bilder in einem PDF-Dokument mit Aspose.Words für .NET zu komprimieren, folgen Sie diesen Schritten:

 Erstellen Sie eine Instanz des`Document` Klasse, die den Pfad zum Word-Dokument angibt.

 Erstellen Sie eine Instanz des`PdfSaveOptions` Klasse und legen Sie die`ImageCompression`Eigentum an`PdfImageCompression.Jpeg` um die JPEG-Komprimierung zu verwenden.

Sie können auch andere Bildkomprimierungsoptionen, wie beispielsweise die JPEG-Qualität, entsprechend Ihren Anforderungen einstellen.

 Verwenden Sie die`Save` Methode der`Document`Klasse, um das Dokument durch Angabe von Speicheroptionen im PDF-Format zu speichern.

#### F: Was ist der Unterschied zwischen Standard-Bildkomprimierung und PDF/A-2u-Bildkomprimierung?
A: Die Standard-Bildkomprimierung reduziert die Größe von Bildern in einem PDF-Dokument, während die Formularfelder erhalten bleiben. Dadurch wird die Gesamtgröße der PDF-Datei reduziert, ohne die Funktionalität der Formularfelder zu beeinträchtigen.

Die Bildkomprimierung mit PDF/A-2u ist eine Zusatzoption, mit der Sie eine PDF-Datei erstellen können, die dem PDF/A-2u-Standard entspricht und gleichzeitig eine Bildkomprimierung anwendet. PDF/A-2u ist ein ISO-Standard für archivierbare PDF-Dokumente und gewährleistet die langfristige Aufbewahrung von Dokumenten.
