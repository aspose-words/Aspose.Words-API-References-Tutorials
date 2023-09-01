---
title: Bildkomprimierung in einem PDF-Dokument
linktitle: Bildkomprimierung in einem PDF-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Komprimieren von Bildern in einem PDF-Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/image-compression/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion „Bildkomprimierung in einem PDF-Dokument“ mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie Bilder in einem Dokument komprimieren und eine PDF-Datei mit der richtigen Bildkomprimierung erstellen.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument hoch

Als nächstes müssen wir das Dokument laden, das wir verarbeiten möchten. In diesem Beispiel gehen wir davon aus, dass das Dokument „Rendering.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Konfigurieren Sie die Optionen zum Speichern als PDF mit Bildkomprimierung

 Um Bilder beim Konvertieren in PDF zu komprimieren, müssen wir das konfigurieren`PdfSaveOptions` Objekt. Bei Bedarf können wir den Bildkomprimierungstyp, die JPEG-Qualität und andere PDF-Konformitätsoptionen festlegen.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Schritt 4: Dokument als PDF mit Bildkomprimierung speichern

Schließlich können wir das Dokument mit den zuvor konfigurierten Speicheroptionen im PDF-Format speichern.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Schritt 5: Konfigurieren Sie Optionen zum Speichern in PDF/A-2u mit Bildkomprimierung

Wenn Sie PDF/A-2u-konforme PDFs mit Bildkomprimierung erstellen möchten, können Sie die zusätzlichen Speicheroptionen konfigurieren.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Verwenden Sie die JPEG-Komprimierung mit 50 % Qualität, um die Dateigröße zu reduzieren.
};
```

## Schritt 6: Speichern Sie das Dokument als PDF/A-2u mit Bildkomprimierung

Speichern Sie das Dokument im PDF/A-2u-Format mit den zuvor konfigurierten zusätzlichen Speicheroptionen.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Das ist alles ! Sie haben die Bilder in einem Dokument erfolgreich komprimiert und mit Aspose.Words für .NET eine PDF-Datei mit ordnungsgemäßer Bildkomprimierung generiert.

### Beispielquellcode zum Komprimieren von Bildern mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
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
		JpegQuality = 100, // Verwenden Sie die JPEG-Komprimierung mit 50 % Qualität, um die Dateigröße zu reduzieren.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Abschluss

In diesem Tutorial haben wir erklärt, wie man Bilder in einem PDF-Dokument mit Aspose.Words für .NET komprimiert. Wenn Sie die beschriebenen Schritte befolgen, können Sie die Größe der Bilder in Ihrem PDF-Dokument ganz einfach reduzieren und ein PDF mit der richtigen Bildkomprimierung erstellen. Nutzen Sie die Bildkomprimierungsfunktionen von Aspose.Words für .NET, um die Größe Ihrer PDF-Dokumente zu optimieren und gleichzeitig die Bildqualität beizubehalten.

### Häufig gestellte Fragen

#### F: Was ist Bildkomprimierung in einem PDF-Dokument?
A: Durch das Komprimieren von Bildern in einem PDF-Dokument wird die Größe der im PDF-Dokument enthaltenen Bilder reduziert, um die Gesamtgröße der PDF-Datei zu verringern. Dies reduziert den benötigten Speicherplatz und verbessert die Leistung beim Laden und Anzeigen der PDF-Datei.

#### F: Wie kann ich Bilder in einem PDF-Dokument mit Aspose.Words für .NET komprimieren?
A: Um Bilder in einem PDF-Dokument mit Aspose.Words für .NET zu komprimieren, gehen Sie folgendermaßen vor:

 Erstellen Sie eine Instanz von`Document` Klasse, die den Pfad zum Word-Dokument angibt.

 Erstellen Sie eine Instanz von`PdfSaveOptions` Klasse und legen Sie die fest`ImageCompression` Eigentum zu`PdfImageCompression.Jpeg` um die JPEG-Komprimierung zu verwenden.

Sie können je nach Bedarf auch andere Bildkomprimierungsoptionen einstellen, z. B. die JPEG-Qualität.

 Benutzen Sie die`Save` Methode der`Document`Klasse zum Speichern des Dokuments im PDF-Format durch Angabe von Speicheroptionen.

#### F: Was ist der Unterschied zwischen der Standard-Bildkomprimierung und der PDF/A-2u-Bildkomprimierung?
A: Die standardmäßige Bildkomprimierung reduziert die Größe von Bildern in einem PDF-Dokument und behält gleichzeitig die Formularfelder bei. Dadurch wird die Gesamtgröße der PDF-Datei reduziert, ohne die Funktionalität der Formularfelder zu beeinträchtigen.

Die Bildkomprimierung mit PDF/A-2u ist eine zusätzliche Option, mit der Sie unter Anwendung der Bildkomprimierung eine PDF-Datei generieren können, die dem PDF/A-2u-Standard entspricht. PDF/A-2u ist ein ISO-Standard für archivierte PDF-Dokumente und garantiert die langfristige Aufbewahrung von Dokumenten.
