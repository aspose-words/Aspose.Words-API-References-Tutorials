---
title: Konvertieren Sie Docx in Mhtml und senden Sie E-Mails
linktitle: Konvertieren Sie Docx in Mhtml und senden Sie E-Mails
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Word-Dokumente von Docx in MHTML konvertieren und sie mit Aspose.Words und Aspose.Email als E-Mails versenden. Schritt-für-Schritt-Anleitung.
type: docs
weight: 10
url: /de/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET ein Word-Dokument im Docx-Format in MHTML konvertieren und es mit Aspose.Email als E-Mail versenden. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

 Stellen Sie zunächst sicher, dass in Ihrer Entwicklungsumgebung sowohl die Bibliotheken Aspose.Words für .NET als auch Aspose.Email installiert und eingerichtet sind. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliotheken herunter und installieren Sie sie[Aspose.Releases](https://releases.aspose.com/words/net/).

## Schritt 1: Initialisieren des Dokumentobjekts

 Initialisieren Sie zunächst die`Document`Objekt mit dem Pfad zu Ihrem Quelldokument im Docx-Format:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Schritt 2: Speichern des Dokuments im MHTML-Format

 Speichern Sie als Nächstes das Dokument in einem`Stream` Objekt im MHTML-Format:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Schritt 3: Zurückspulen des Streams

Da Aspose.Email den Stream von Anfang an lesen muss, spulen Sie den Stream an den Anfang zurück:

```csharp
stream.Position = 0;
```

## Schritt 4: Erstellen einer Aspose.Email MIME-Nachricht

 Ein ... kreieren`MailMessage` Objekt aus dem Stream mit`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Sie können die Nachrichteneigenschaften wie Absender, Empfänger und Betreff jederzeit anpassen.

## Schritt 5: Senden der E-Mail

 Verwenden Sie Aspose.Email`SmtpClient` Um die E-Mail zu senden:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Stellen Sie sicher, dass Sie die richtige Hostadresse des SMTP-Servers angeben.

Das ist es! Sie haben ein Word-Dokument im Docx-Format erfolgreich in MHTML konvertiert und es mit Aspose.Words für .NET und Aspose.Email als E-Mail versendet.

### Beispielquellcode für Docx To Mhtml und das Senden von E-Mails mit Aspose.Words für .NET

```csharp

	// Document doc = new Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Spulen Sie den Stream an den Anfang zurück, damit Aspose.Email ihn lesen kann.
	stream.Position = 0;

	// Erstellen Sie eine Aspose.Email MIME-E-Mail-Nachricht aus dem Stream.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Senden Sie die Nachricht mit Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.

### FAQs

#### Wie konvertiert man eine DOCX-Datei in MHTML?

Um eine DOCX-Datei in MHTML zu konvertieren, können Sie Softwaretools oder Bibliotheken verwenden, die diese Funktionalität bereitstellen. Aspose.Words für .NET ist eine zuverlässige Option für diese Konvertierung. Mit der Bibliotheks-API können Sie die DOCX-Datei laden und im MHTML-Format speichern.

#### Wie versende ich eine E-Mail mit einem MHTML-Dateianhang?

Um eine E-Mail mit einer MHTML-Datei als Anhang zu senden, können Sie Bibliotheken oder Tools verwenden, die speziell für den E-Mail-Versand konzipiert sind, z. B. System.Net.Mail in .NET. Sie müssen eine E-Mail-Nachricht erstellen, den Empfänger, den Betreff und den Inhalt angeben und dann die MHTML-Datei als Anhang zur Nachricht hinzufügen, bevor Sie sie senden.

#### Welche Einschränkungen gibt es bei der E-Mail-Konvertierung und dem E-Mail-Versand?

Die Einschränkungen des E-Mail-Konvertierungs- und Versandprozesses hängen von den spezifischen Tools ab, die Sie verwenden. Für einige Tools gelten möglicherweise Einschränkungen hinsichtlich der Dateigröße, der Sicherheitseinstellungen oder der unterstützten E-Mail-Protokolle. Es ist wichtig, Tools auszuwählen, die Ihren Anforderungen entsprechen, und diese Einschränkungen bei der Implementierung zu berücksichtigen.

#### Ist Aspose ein zuverlässiges Tool für die Konvertierung von DOCX in MHTML und den E-Mail-Versand?

Ja, Aspose.Words für .NET ist ein zuverlässiges Tool für die Konvertierung von DOCX in MHTML und den E-Mail-Versand. Aufgrund seiner Leistung und Qualität wird es häufig von Entwicklern und Fachleuten verwendet. Das Tool bietet umfassende Dokumentation, erweiterte Funktionen und engagierten technischen Support und ist daher eine empfehlenswerte Wahl für diese Aufgaben.