---
title: PDF zu Docx
linktitle: PDF zu Docx
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie PDF-Dokumente mit Aspose.Words für .NET in das Docx-Format konvertieren. Schritt-für-Schritt-Anleitung mit Beispielquellcode.
type: docs
weight: 10
url: /de/net/basic-conversions/pdf-to-docx/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET ein PDF-Dokument in das Docx-Format konvertieren. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document` Objekt, indem Sie den Pfad zu Ihrem PDF-Dokument angeben:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Schritt 2: Speichern des Dokuments im Docx-Format

 Speichern Sie als Nächstes das Dokument im Docx-Format, indem Sie das aufrufen`Save` Methode auf der`Document`Objekt und Angabe des Pfads und Dateinamens für das ausgegebene Docx-Dokument:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein PDF-Dokument in das Docx-Format konvertiert.

### Beispielquellcode für Pdf To Docx mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
	
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.