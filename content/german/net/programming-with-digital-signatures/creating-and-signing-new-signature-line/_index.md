---
title: Erstellen und Signieren einer neuen Signaturzeile
linktitle: Erstellen und Signieren einer neuen Signaturzeile
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine neue Signaturzeile in einem Word-Dokument erstellt und signiert. Wenn Sie die bereitgestellten Schritte befolgen, können Sie ganz einfach eine Signaturzeile in Ihr Dokument einfügen, seine Optionen anpassen und das Dokument mit einem digitalen Zertifikat signieren. Das Hinzufügen von Signaturzeilen und digitalen Signaturen zu Ihren Dokumenten erhöht deren Authentizität und Integrität und macht sie sicherer und vertrauenswürdiger. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Signaturen und digitalen Zertifikaten in Word-Dokumenten, sodass Sie den Signaturprozess automatisieren und die Gültigkeit Ihrer Dokumente sicherstellen können.

### FAQs

#### F: Was ist eine Signaturzeile in einem Word-Dokument?

A: Eine Signaturzeile in einem Word-Dokument ist ein Platzhalter, der angibt, wo eine Signatur platziert werden soll. Es enthält in der Regel den Namen, den Titel und das Datum und bietet Platz für eine handschriftliche oder digitale Unterschrift.

#### F: Wie kann ich mit Aspose.Words für .NET eine Signaturzeile in einem Word-Dokument erstellen?

A: Um mit Aspose.Words für .NET eine Signaturzeile in einem Word-Dokument zu erstellen, können Sie die folgenden Schritte ausführen:
1.  Erstellen Sie eine Instanz von`Document` Klasse und a`DocumentBuilder` Objekt.
2.  Benutzen Sie die`InsertSignatureLine` Methode der`DocumentBuilder` Objekt, um eine neue Signaturzeile in das Dokument einzufügen.
3. Speichern Sie das geänderte Dokument.

#### F: Kann ich die Optionen der Signaturzeile anpassen, z. B. Name, Titel und Datum?

 A: Ja, Sie können die Optionen für die Signaturzeile anpassen. Der`SignatureLineOptions` Die Klasse stellt Eigenschaften bereit, um die gewünschten Optionen festzulegen, z`Signer`, `SignerTitle`, `ShowDate`usw. Sie können diese Eigenschaften ändern, bevor Sie die Signaturzeile einfügen.

#### F: Wie kann ich das Dokument signieren, nachdem ich eine Signaturzeile erstellt habe?

 A: Um das Dokument nach dem Erstellen einer Signaturzeile zu signieren, müssen Sie die Signaturoptionen festlegen und verwenden`DigitalSignatureUtil` Klasse. Hier sind die Schritte:
1.  Stellen Sie die ein`SignatureLineId` Eigentum in der`SignOptions` Objekt auf die ID der Signaturzeile.
2.  Stellen Sie die ein`SignatureLineImage` Eigentum in der`SignOptions` widersprechen Sie dem Bild der Signatur, das Sie verwenden möchten.
3.  Laden Sie das Signaturzertifikat mit`CertificateHolder` Klasse.
4.  Benutzen Sie die`DigitalSignatureUtil.Sign` Methode zum Signieren des Dokuments unter Bereitstellung der erforderlichen Parameter.

#### F: Kann ich ein digitales Signaturbild zum Signieren des Dokuments verwenden?

 A: Ja, Sie können ein digitales Signaturbild zum Signieren des Dokuments verwenden. Dazu müssen Sie die Bilddatei im bereitstellen`SignOptions` Objekt mit dem`SignatureLineImage`Eigentum. Das Bild kann in jedem unterstützten Bildformat vorliegen, z. B. JPEG, PNG oder EMF.

#### F: Wozu dient das Erstellen und Signieren einer neuen Signaturzeile in einem Word-Dokument?

A: Durch das Erstellen und Signieren einer neuen Signaturzeile in einem Word-Dokument mit Aspose.Words für .NET können Sie einen Platzhalter für eine Signatur hinzufügen und das Dokument dann mit einem digitalen Zertifikat signieren. Dieser Prozess gewährleistet die Authentizität und Integrität des Dokuments und liefert den Nachweis der Genehmigung oder Zustimmung.

#### F: Kann ich mit Aspose.Words für .NET mehrere Signaturzeilen in einem Word-Dokument erstellen und signieren?

A: Ja, Sie können mit Aspose.Words für .NET mehrere Signaturzeilen in einem Word-Dokument erstellen und signieren. Jede Signaturzeile kann ihre eigene eindeutige ID und Optionen haben. Sie können die Schritte wiederholen, um weitere Signaturzeilen im Dokument zu erstellen und zu signieren.

#### F: Kann ich die Signaturzeile ändern oder zusätzliche Informationen hinzufügen, nachdem sie signiert wurde?

A: Sobald eine Signaturzeile signiert wurde, wird sie Teil des Dokumentinhalts und kann nicht separat geändert werden. Sie können jedoch nach der signierten Signaturzeile zusätzliche Informationen oder Inhalte hinzufügen.

#### F: Kann ich die digitale Signatur eines Dokuments überprüfen, das eine Signaturzeile enthält?

 A: Ja, Aspose.Words für .NET bietet Funktionen zum Überprüfen der digitalen Signatur eines Dokuments, das eine Signaturzeile enthält. Du kannst den ... benutzen`DigitalSignatureUtil.Verify` Methode zur Überprüfung der Gültigkeit und Authentizität der digitalen Signatur.

#### F: Welches Dateiformat unterstützt Aspose.Words für .NET zum Erstellen und Signieren von Signaturzeilen?

A: Aspose.Words für .NET unterstützt das Erstellen und Signieren von Signaturzeilen im DOCX-Dateiformat. Mit den bereitgestellten Methoden und Klassen können Sie Signaturzeilen in DOCX-Dateien erstellen und signieren.