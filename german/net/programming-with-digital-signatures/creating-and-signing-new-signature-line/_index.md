---
title: Erstellen und Signieren einer neuen Signaturzeile
linktitle: Erstellen und Signieren einer neuen Signaturzeile
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine neue Signaturzeile in einem Word-Dokument erstellen und signieren.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---

In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion zum Erstellen und Signieren einer neuen Signaturzeile mit Aspose.Words für .NET. Mit dieser Funktion können Sie eine Signaturzeile in ein Word-Dokument einfügen, benutzerdefinierte Optionen festlegen und das Dokument signieren. Folgen Sie den unteren Schritten:

## Schritt 1: Dokument und Generator erstellen

Erstellen Sie zunächst eine Instanz der Document-Klasse und ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Einfügen der Signaturzeile

Verwenden Sie die Methode InsertSignatureLine() des DocumentBuilder-Objekts, um eine neue Signaturzeile in das Dokument einzufügen:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Schritt 3: Speichern Sie das Dokument

Speichern Sie das geänderte Dokument:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen zum Speichern des Dokuments angeben.

## Schritt 4: Unterschreiben des Dokuments

Um das Dokument zu signieren, müssen Sie die Signaturoptionen festlegen und die DigitalSignatureUtil-Klasse verwenden:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Stellen Sie sicher, dass Sie die richtigen Pfade für das Dokument, das Signaturzeilenbild und das signierte Dokument angeben.

### Beispielquellcode zum Erstellen und Signieren einer neuen Signaturzeile mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Erstellen und Signieren einer neuen Signaturzeile mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach eine neue Signaturzeile in Ihrem Word-Dokument erstellen und signieren.

