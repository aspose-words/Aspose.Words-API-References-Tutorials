---
title: Digitale Signatur in Word-Dokument erkennen
linktitle: Digitale Signatur in Word-Dokument erkennen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Erkennen digitaler Signaturen in Word-Dokumenten mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-fileformat/detect-document-signatures/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion zur Erkennung digitaler Signaturen in Word-Dokumenten mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie wissen, wie Sie digitale Signaturen in einem Dokument erkennen.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Dokumentverzeichnis festlegen

 Zunächst müssen Sie den Pfad zum Verzeichnis angeben, in dem sich Ihre Dokumente befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Digitale Signaturen erkennen

 Als nächstes verwenden wir die`DetectFileFormat` Methode der`FileFormatUtil` Klasse zum Erkennen der Dateiformatinformationen. In diesem Beispiel gehen wir davon aus, dass das Dokument „Digitally signature.docx“ heißt und sich im angegebenen Dokumentverzeichnis befindet.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## Schritt 3: Auf digitale Signaturen prüfen

 Wir prüfen, ob das Dokument digitale Signaturen enthält, mit dem`HasDigitalSignature` Eigentum der`FileFormatInfo` Objekt. Wenn digitale Signaturen erkannt werden, zeigen wir eine Meldung an, dass die Signaturen verloren gehen, wenn das Dokument mit Aspose.Words geöffnet/gespeichert wird.

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

Das ist alles! Sie haben mit Aspose.Words für .NET erfolgreich digitale Signaturen in einem Dokument erkannt.

### Beispielquellcode zum Erkennen von Dokumentsignaturen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```
## Abschluss

Dieses Tutorial bietet Ihnen eine Schritt-für-Schritt-Anleitung zum Erkennen digitaler Signaturen in Word-Dokumenten mithilfe der Funktion zur Erkennung digitaler Signaturen mit Aspose.Words für .NET. Jeder Teil des Codes wurde ausführlich erklärt, sodass Sie verstehen, wie Sie digitale Signaturen in einem Dokument erkennen.

### FAQ zum Erkennen digitaler Signaturen in Word-Dokumenten

#### Wie erkennt man mit Aspose.Words für .NET das Vorhandensein einer digitalen Signatur in einem Word-Dokument?

 Um das Vorhandensein einer digitalen Signatur in einem Word-Dokument mit Aspose.Words für .NET zu erkennen, können Sie die im Tutorial beschriebenen Schritte befolgen. Mit dem`DetectFileFormat` Methode der`FileFormatUtil` Klasse ermöglicht es Ihnen, Dateiformatinformationen zu erkennen. Dann können Sie die`HasDigitalSignature` Eigentum der`FileFormatInfo`Objekt, um festzustellen, ob das Dokument eine digitale Signatur enthält. Wenn eine digitale Signatur erkannt wird, können Sie eine Meldung anzeigen, dass Signaturen verloren gehen, wenn das Dokument mit Aspose.Words geöffnet/gespeichert wird.

#### Wie gebe ich das Verzeichnis mit den Dokumenten an, in denen nach der digitalen Signatur gesucht werden soll?

 Um das Verzeichnis anzugeben, das die Dokumente enthält, in denen Sie nach der digitalen Signatur suchen möchten, müssen Sie die`dataDir` Variable im Code. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

#### Welchen Einfluss hat das Öffnen/Speichern eines Dokuments mit Aspose.Words auf digitale Signaturen?

Wenn Sie ein Dokument mit Aspose.Words öffnen oder speichern, gehen die im Dokument vorhandenen digitalen Signaturen verloren. Dies liegt an Änderungen, die während der Verarbeitung mit Aspose.Words am Dokument vorgenommen wurden. Wenn Sie digitale Signaturen beibehalten müssen, sollten Sie dies berücksichtigen und eine andere Methode zum Verwalten von Dokumenten mit digitalen Signaturen verwenden.

#### Welche anderen Funktionen von Aspose.Words für .NET können in Verbindung mit der digitalen Signaturerkennung verwendet werden?

 Aspose.Words für .NET bietet eine Vielzahl von Funktionen zum Verarbeiten und Bearbeiten von Word-Dokumenten. Neben der Erkennung digitaler Signaturen können Sie mit der Bibliothek auch Text, Bilder oder Metadaten aus Dokumenten extrahieren, Formatierungsänderungen vornehmen, Dokumente zusammenführen, Dokumente in andere Formate konvertieren und vieles mehr. Sie können die[Aspose.Words für .NET API-Referenzen](https://reference.aspose.com/words/net/) um alle verfügbaren Funktionen zu entdecken und die zu finden, die Ihren Anforderungen am besten entsprechen.

#### Welche Einschränkungen gibt es beim Erkennen digitaler Signaturen mit Aspose.Words für .NET?

Die Erkennung digitaler Signaturen mit Aspose.Words für .NET beschränkt sich auf die Erkennung des Vorhandenseins von Signaturen in einem Dokument. Aspose.Words bietet jedoch keine Funktion zur Überprüfung der Authentizität oder Integrität digitaler Signaturen. Um erweiterte Vorgänge an digitalen Signaturen durchzuführen, müssen Sie andere spezialisierte Tools oder Bibliotheken verwenden.