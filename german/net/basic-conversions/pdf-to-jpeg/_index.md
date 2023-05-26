---
title: PDF in JPEG
linktitle: PDF in JPEG
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET PDF-Dokumente in JPEG-Bilder konvertieren. Schritt-für-Schritt-Anleitung mit Beispielquellcode.
type: docs
weight: 10
url: /de/net/basic-conversions/pdf-to-jpeg/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET ein PDF-Dokument in JPEG-Bilder konvertieren. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document` Objekt, indem Sie den Pfad zu Ihrem PDF-Dokument angeben:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Schritt 2: Speichern des Dokuments als JPEG-Bilder

 Speichern Sie als Nächstes das Dokument als JPEG-Bilder, indem Sie die Datei aufrufen`Save` Methode auf der`Document` Objekt und Angabe des Pfads und Dateinamens für die ausgegebenen JPEG-Bilder:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein PDF-Dokument in JPEG-Bilder konvertiert.

### Beispielquellcode für PDF in JPEG mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");

```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.