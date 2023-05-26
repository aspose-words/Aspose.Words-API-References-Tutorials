---
title: Dokument unterschreiben
linktitle: Dokument unterschreiben
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie ein Word-Dokument mit Aspose.Words für .NET digital signieren.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/sign-document/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion zum Signieren von Dokumenten mit Aspose.Words für .NET. Mit dieser Funktion können Sie ein Word-Dokument mithilfe eines Zertifikats digital signieren. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Zertifikats

Laden Sie zunächst das Signaturzertifikat mithilfe der CertificateHolder-Klasse:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Zertifikat und das zugehörige Passwort angeben.

## Schritt 2: Unterschreiben des Dokuments

Verwenden Sie die DigitalSignatureUtil-Klasse, um das Dokument zu signieren:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Stellen Sie sicher, dass Sie die richtigen Pfade für das Quelldokument und das signierte Dokument angeben.

### Beispielquellcode für Sign Document mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Signieren eines Dokuments mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Wenn Sie diese Schritte befolgen, können Sie ganz einfach ein Word-Dokument mit Aspose.Words für .NET signieren.



