---
title: Txt an Docx
linktitle: Txt an Docx
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET reine Textdateien (Txt) in Word-Dokumente (Docx) konvertieren. Schritt-für-Schritt-Anleitung mit Beispielcode.
type: docs
weight: 10
url: /de/net/basic-conversions/txt-to-docx/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET eine reine Textdatei (Txt) in ein Word-Dokument im Docx-Format konvertieren. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document` -Objekt, indem Sie den Pfad zu Ihrer Nur-Text-Datei angeben:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "English text.txt");
```

## Schritt 2: Speichern des Dokuments im Docx-Format

 Speichern Sie als Nächstes das Dokument im Docx-Format, indem Sie das aufrufen`Save` Methode auf der`Document`Objekt und Angabe des Pfads und Dateinamens für das ausgegebene Docx-Dokument:

```csharp
doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich eine reine Textdatei (Txt) in ein Word-Dokument im Docx-Format konvertiert.

### Beispielquellcode für Txt To Docx mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Die Kodierung der Textdatei wird automatisch erkannt.
	Document doc = new Document(MyDir + "English text.txt");

	doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");

```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.