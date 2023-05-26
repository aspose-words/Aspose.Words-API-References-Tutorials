---
title: Docx zu PDF
linktitle: Docx zu PDF
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Word-Dokumente mit Aspose.Words für .NET von Docx in PDF konvertieren. Schritt-für-Schritt-Anleitung mit Beispielquellcode.
type: docs
weight: 10
url: /de/net/basic-conversions/docx-to-pdf/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET ein Word-Dokument im Docx-Format in PDF konvertieren. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document` Objekt mit dem Pfad zu Ihrem Quelldokument im Docx-Format:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Schritt 2: Speichern des Dokuments im PDF-Format

 Speichern Sie anschließend das Dokument im PDF-Format, indem Sie die aufrufen`Save` Methode auf der`Document` Objekt und Angabe des Pfads und Dateinamens für das ausgegebene PDF-Dokument:

```csharp
doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Word-Dokument im Docx-Format in PDF konvertiert.

### Beispielquellcode für Docx To Pdf mit Aspose.Words für .NET

```csharp

	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
	
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.
