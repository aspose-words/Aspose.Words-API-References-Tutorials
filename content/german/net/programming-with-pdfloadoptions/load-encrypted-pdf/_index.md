---
title: Verschlüsseltes PDF laden
linktitle: Verschlüsseltes PDF laden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Laden einer verschlüsselten PDF-Datei mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

Bei der Textverarbeitung mit PDF-Dokumenten in Ihrer .NET-Anwendung kann es erforderlich sein, kennwortgeschützte PDF-Dateien zu laden. Aspose.Words für .NET ist eine leistungsstarke Bibliothek, die Funktionen zum Laden verschlüsselter PDF-Dokumente bietet. In diesem Artikel führen wir Sie Schritt für Schritt durch das Verständnis und die Verwendung dieser Funktion.

## Informationen zur Funktion „Verschlüsselte PDF laden“

Mit der Funktion „Verschlüsselte PDFs laden“ von Aspose.Words für .NET können Sie kennwortgeschützte PDF-Dateien laden. Sie können das Kennwort beim Laden des Dokuments angeben, damit Sie auf den Inhalt zugreifen und ihn nach Bedarf bearbeiten können.

## Schritt 1: Laden des verschlüsselten PDF-Dokuments

Der erste Schritt besteht darin, das verschlüsselte PDF-Dokument in Ihre Anwendung zu laden. So geht's:

```csharp
//Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Achten Sie darauf, den korrekten Pfad zur verschlüsselten PDF-Datei im`dataDir` Variable.

## Schritt 2: Verschlüsseln des PDF-Dokuments

 Wenn Sie Ihr PDF-Dokument zusätzlich verschlüsseln möchten, können Sie dies mit dem`PdfSaveOptions` Klasse und Angabe der Verschlüsselungsdetails:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Dadurch wird eine verschlüsselte Version des PDF-Dokuments im angegebenen Verzeichnis erstellt.

## Schritt 3: Speichern des verschlüsselten PDF-Dokuments

Nach dem Hochladen und optionalen Verschlüsseln des PDF-Dokuments können Sie dieses entsprechend Ihren spezifischen Anforderungen in einem anderen Format speichern oder weiterverarbeiten.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Schritt 5: Laden des verschlüsselten PDF-Dokuments mit Passwort

Wartung

Wenn Sie jedoch das verschlüsselte PDF-Dokument mit einem Passwort laden möchten, müssen Sie den`PdfLoadOptions` Klasse und geben Sie das Passwort beim Laden des Dokuments an:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 Geben Sie unbedingt das richtige Passwort im`Password` Variable.

### Beispiel-Quellcode zum Laden verschlüsselter PDFs mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## Abschluss

In diesem Artikel haben wir untersucht, wie Sie die Funktion „Verschlüsselte PDFs laden“ von Aspose.Words für .NET verwenden. Sie haben gelernt, wie Sie verschlüsselte PDF-Dateien hochladen, wie Sie ein PDF-Dokument verschlüsseln, wie Sie ein verschlüsseltes PDF mit einem Kennwort hochladen und wie Sie eine Ausgabe im Markdown-Format generieren. Diese Funktion ist bei der Textverarbeitung mit sicheren PDF-Dokumenten äußerst nützlich.


