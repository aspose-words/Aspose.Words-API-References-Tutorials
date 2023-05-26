---
title: Vorhandene Signaturzeile signieren
linktitle: Vorhandene Signaturzeile signieren
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine vorhandene Signaturzeile in einem Word-Dokument signieren.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/signing-existing-signature-line/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Signaturfunktion einer vorhandenen Signaturzeile mit Aspose.Words für .NET. Mit dieser Funktion können Sie eine bereits in einem Word-Dokument vorhandene Signaturzeile digital signieren. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments und Zugriff auf die Signaturzeile

Laden Sie zunächst das Dokument hoch, das die vorhandene Signaturzeile enthält:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Schritt 2: Signaturoptionen festlegen

Erstellen Sie eine Instanz der SignOptions-Klasse und legen Sie die Signaturoptionen fest, einschließlich der Signaturzeilen-ID und des Signaturzeilenbilds:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Stellen Sie sicher, dass Sie den richtigen Pfad zum Signaturzeilenbild angeben.

## Schritt 3: Laden des Zertifikats

Laden Sie zunächst das Signaturzertifikat mithilfe der CertificateHolder-Klasse:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem Zertifikat und das zugehörige Passwort angeben.

## Schritt 4: Signieren der vorhandenen Signaturzeile

Verwenden Sie die DigitalSignatureUtil-Klasse, um die vorhandene Signaturzeile zu signieren:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Stellen Sie sicher, dass Sie die richtigen Pfade für das Quelldokument, das signierte Dokument und das Zertifikat angeben.

### Beispielquellcode zum Signieren einer vorhandenen Signaturzeile mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Signieren einer vorhandenen Signaturzeile mit Aspose.Words für .NET:


```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach eine vorhandene Signaturzeile in einem Word-Dokument signieren.

