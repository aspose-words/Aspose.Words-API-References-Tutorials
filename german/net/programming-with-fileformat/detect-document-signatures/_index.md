---
title: Dokumentsignaturen erkennen
linktitle: Dokumentsignaturen erkennen
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erkennen digitaler Signaturen in einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-fileformat/detect-document-signatures/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Dokumentsignaturerkennungsfunktion mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie verstehen, wie Sie digitale Signaturen in einem Dokument erkennen.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Zunächst müssen Sie den Pfad zu dem Verzeichnis definieren, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Digitale Signaturen erkennen

 Als nächstes verwenden wir die`DetectFileFormat` Methode der`FileFormatUtil` Klasse zum Erkennen der Dateiformatinformationen. In diesem Beispiel gehen wir davon aus, dass das Dokument „Digitally signiert.docx“ heißt und sich im angegebenen Dokumentenverzeichnis befindet.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## Schritt 3: Suchen Sie nach digitalen Signaturen

 Wir prüfen, ob das Dokument digitale Signaturen enthält`HasDigitalSignature` Eigentum der`FileFormatInfo` Objekt. Wenn digitale Signaturen erkannt werden, zeigen wir eine Meldung an, dass die Signaturen verloren gehen, wenn das Dokument mit Aspose.Words geöffnet/gespeichert wird.

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

Das ist alles ! Sie haben mit Aspose.Words für .NET erfolgreich digitale Signaturen in einem Dokument erkannt.

### Beispielquellcode zum Erkennen von Dokumentsignaturen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```
