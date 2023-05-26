---
title: Legen Sie die Signaturanbieter-ID fest
linktitle: Legen Sie die Signaturanbieter-ID fest
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Signaturanbieter-ID in einem Word-Dokument festlegen.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/set-signature-provider-id/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion „Signaturanbieter-ID festlegen“ mit Aspose.Words für .NET. Mit dieser Funktion können Sie die Signaturanbieter-ID für eine Signaturzeile in einem Word-Dokument angeben. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments und Zugriff auf die Signaturzeile

Laden Sie zunächst das Dokument hoch, das die Signaturzeile enthält:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Schritt 2: Signaturoptionen festlegen

Erstellen Sie eine Instanz der SignOptions-Klasse und legen Sie die Signaturoptionen fest, einschließlich der Anbieter-ID:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Schritt 3: Unterschreiben des Dokuments

Um das Dokument zu signieren, müssen Sie die Klasse DigitalSignatureUtil verwenden und das Signaturzertifikat angeben:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Stellen Sie sicher, dass Sie die richtigen Pfade für das Dokument, das Zertifikat und das signierte Dokument angeben.

### Beispielquellcode für Set Signature Provider Id mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Festlegen der Signaturanbieter-ID mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Vervollständigen Sie die Signaturanbieter-ID in Ihrem Word-Dokument mit Aspose.Words für .NET.

