---
title: Verschlüsseltes Dokument signieren
linktitle: Verschlüsseltes Dokument signieren
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie ein verschlüsseltes Dokument mit Aspose.Words für .NET digital signieren.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/signing-encrypted-document/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion zum Signieren eines verschlüsselten Dokuments mit Aspose.Words für .NET. Mit dieser Funktion können Sie ein Word-Dokument digital signieren, das mit einem Entschlüsselungskennwort verschlüsselt ist. Folgen Sie den unteren Schritten:

## Schritt 1: Signaturoptionen festlegen

Erstellen Sie eine Instanz der SignOptions-Klasse und legen Sie das Entschlüsselungskennwort fest:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Stellen Sie sicher, dass Sie das richtige Entschlüsselungskennwort für Ihr verschlüsseltes Dokument angeben.

## Schritt 2: Laden des Zertifikats

Laden Sie zunächst das Signaturzertifikat mithilfe der CertificateHolder-Klasse:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Zertifikat und das zugehörige Passwort angeben.

## Schritt 3: Signieren des verschlüsselten Dokuments

Verwenden Sie die DigitalSignatureUtil-Klasse, um das verschlüsselte Dokument zu signieren:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Stellen Sie sicher, dass Sie die richtigen Pfade für das verschlüsselte Dokument, das signierte Dokument und das Zertifikat angeben.

### Beispielquellcode zum Signieren eines verschlüsselten Dokuments mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Signieren eines verschlüsselten Dokuments mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Wenn Sie diese Schritte befolgen, können Sie ganz einfach ein verschlüsseltes Word-Dokument mit Aspose.Words für .NET signieren.

