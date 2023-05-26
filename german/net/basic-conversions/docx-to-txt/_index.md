---
title: Docx zu Txt
linktitle: Docx zu Txt
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Word-Dokumente von Docx in einfachen Text (Txt) konvertieren. Schritt-für-Schritt-Anleitung mit Beispielquellcode.
type: docs
weight: 10
url: /de/net/basic-conversions/docx-to-txt/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET ein Word-Dokument im Docx-Format in einfachen Text (Txt) konvertieren. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document` Objekt mit dem Pfad zu Ihrem Quelldokument im Docx-Format:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Schritt 2: Speichern des Dokuments im Txt-Format

 Speichern Sie als Nächstes das Dokument im Nur-Text-Format (Txt), indem Sie die aufrufen`Save` Methode auf der`Document` Objekt und Angabe des Pfads und Dateinamens für das ausgegebene Txt-Dokument:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Word-Dokument im Docx-Format in einfachen Text (Txt) konvertiert.

### Beispielquellcode für Docx To Txt mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");

```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.