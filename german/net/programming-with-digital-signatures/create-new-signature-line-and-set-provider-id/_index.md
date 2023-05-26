---
title: Erstellen Sie eine neue Signaturzeile und legen Sie die Anbieter-ID fest
linktitle: Erstellen Sie eine neue Signaturzeile und legen Sie die Anbieter-ID fest
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine neue Signaturzeile erstellen und die Anbieter-ID in einem Word-Dokument festlegen.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion „Neue Signaturzeile erstellen und Anbieter-ID festlegen“ mit Aspose.Words für .NET. Mit dieser Funktion können Sie eine Signaturzeile in ein Word-Dokument einfügen, benutzerdefinierte Optionen festlegen und das Dokument signieren. Folgen Sie den unteren Schritten:

## Schritt 1: Dokument und Generator erstellen

Erstellen Sie zunächst eine Instanz der Document-Klasse und ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Signaturzeilenoptionen festlegen

Erstellen Sie eine Instanz der SignatureLineOptions-Klasse und legen Sie die gewünschten Optionen fest:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Schritt 3: Einfügen der Signaturzeile

Verwenden Sie die Methode InsertSignatureLine() des DocumentBuilder-Objekts, um die Signaturzeile in das Dokument einzufügen:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Schritt 4: Anbieter-ID festlegen

Legen Sie die Provider-ID für die Signaturzeile mithilfe der ProviderId-Eigenschaft fest:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Stellen Sie sicher, dass Sie die richtige Anbieter-ID für Ihren Anwendungsfall angeben.

## Schritt 5: Speichern Sie das Dokument

Speichern Sie das geänderte Dokument:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen zum Speichern des Dokuments angeben.

## Schritt 6: Unterschreiben des Dokuments

Um das Dokument zu signieren, müssen Sie die Signaturoptionen festlegen und die DigitalSignatureUtil-Klasse verwenden:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Stellen Sie sicher, dass Sie die richtigen Pfade für das Dokument, das Zertifikat und das signierte Dokument angeben.

### Beispielquellcode für „Neue Signaturzeile erstellen und Anbieter-ID festlegen“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Erstellen einer neuen Signaturzeile und zum Festlegen der Anbieter-ID mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach eine neue Signaturzeile erstellen und die Anbieter-ID in Ihrem Word-Dokument festlegen.

