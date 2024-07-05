---
title: Erstellen und Unterzeichnen einer neuen Signaturzeile
linktitle: Erstellen und Unterzeichnen einer neuen Signaturzeile
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine neue Signaturzeile in einem Word-Dokument erstellen und unterzeichnen.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
In diesem Tutorial führen wir Sie durch die Schritte zum Erstellen und Signieren einer neuen Signaturzeile mit Aspose.Words für .NET. Mit dieser Funktion können Sie eine Signaturzeile in ein Word-Dokument einfügen, benutzerdefinierte Optionen festlegen und das Dokument signieren. Befolgen Sie die folgenden Schritte:

## Schritt 1: Erstellen des Dokuments und des Generators

Beginnen Sie mit der Erstellung einer Instanz der Document-Klasse und eines DocumentBuilder-Objekts:

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

Geben Sie zum Speichern des Dokuments unbedingt den richtigen Pfad und Dateinamen an.

## Schritt 4: Unterzeichnen des Dokuments

Um das Dokument zu signieren, müssen Sie die Signaturoptionen festlegen und die Klasse DigitalSignatureUtil verwenden:

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

Achten Sie darauf, die richtigen Pfade für das Dokument, das Signaturzeilenbild und das signierte Dokument anzugeben.

### Beispielquellcode zum Erstellen und Signieren einer neuen Signaturzeile mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Erstellen und Signieren einer neuen Signaturzeile mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
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

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach eine neue Signaturzeile in Ihrem Word-Dokument erstellen und unterzeichnen.

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine neue Signaturzeile in einem Word-Dokument erstellt und signiert. Indem Sie die angegebenen Schritte befolgen, können Sie ganz einfach eine Signaturzeile in Ihr Dokument einfügen, ihre Optionen anpassen und das Dokument mit einem digitalen Zertifikat signieren. Das Hinzufügen von Signaturzeilen und digitalen Signaturen zu Ihren Dokumenten verbessert deren Authentizität und Integrität und macht sie sicherer und vertrauenswürdiger. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Signaturen und digitalen Zertifikaten in Word-Dokumenten, sodass Sie den Signaturprozess automatisieren und die Gültigkeit Ihrer Dokumente sicherstellen können.

### Häufig gestellte Fragen

#### F: Was ist eine Signaturzeile in einem Word-Dokument?

A: Eine Signaturzeile in einem Word-Dokument ist ein Platzhalter, der angibt, wo eine Signatur platziert werden soll. Sie enthält normalerweise den Namen, den Titel und das Datum und bietet Platz für eine handschriftliche oder digitale Signatur.

#### F: Wie kann ich mit Aspose.Words für .NET eine Signaturzeile in einem Word-Dokument erstellen?

A: Um mit Aspose.Words für .NET eine Signaturzeile in einem Word-Dokument zu erstellen, können Sie diese Schritte befolgen:
1.  Erstellen Sie eine Instanz des`Document` Klasse und eine`DocumentBuilder` Objekt.
2.  Verwenden Sie die`InsertSignatureLine` Methode der`DocumentBuilder` Objekt, um eine neue Signaturzeile in das Dokument einzufügen.
3. Speichern Sie das geänderte Dokument.

#### F: Kann ich die Optionen der Signaturzeile, beispielsweise Name, Titel und Datum, anpassen?

 A: Ja, Sie können die Optionen für die Signaturzeile anpassen.`SignatureLineOptions` Klasse bietet Eigenschaften zum Setzen der gewünschten Optionen, wie zum Beispiel`Signer`, `SignerTitle`, `ShowDate`usw. Sie können diese Eigenschaften ändern, bevor Sie die Signaturzeile einfügen.

#### F: Wie kann ich das Dokument unterzeichnen, nachdem ich eine Signaturzeile erstellt habe?

 A: Um das Dokument nach dem Erstellen einer Signaturzeile zu signieren, müssen Sie die Signaturoptionen festlegen und die`DigitalSignatureUtil` Klasse. Hier sind die Schritte:
1.  Legen Sie die`SignatureLineId` Eigentum in der`SignOptions` Objekt zur ID der Signaturzeile.
2.  Legen Sie die`SignatureLineImage` Eigentum in der`SignOptions` Erheben Sie Einwände gegen das Bild der Signatur, die Sie verwenden möchten.
3.  Laden Sie das Signaturzertifikat mit dem`CertificateHolder` Klasse.
4.  Verwenden Sie die`DigitalSignatureUtil.Sign` Methode zum Signieren des Dokuments unter Angabe der erforderlichen Parameter.

#### F: Kann ich zum Unterzeichnen des Dokuments ein digitales Signaturbild verwenden?

 A: Ja, Sie können ein digitales Signaturbild verwenden, um das Dokument zu unterzeichnen. Dazu müssen Sie die Bilddatei im`SignOptions` Objekt mit dem`SignatureLineImage`Eigenschaft. Das Bild kann in jedem unterstützten Bildformat vorliegen, beispielsweise JPEG, PNG oder EMF.

#### F: Was ist der Zweck des Erstellens und Unterzeichnens einer neuen Signaturzeile in einem Word-Dokument?

A: Wenn Sie mit Aspose.Words für .NET eine neue Signaturzeile in einem Word-Dokument erstellen und signieren, können Sie einen Platzhalter für eine Signatur hinzufügen und das Dokument dann mit einem digitalen Zertifikat signieren. Dieser Prozess stellt die Authentizität und Integrität des Dokuments sicher und liefert den Nachweis der Genehmigung oder Zustimmung.

#### F: Kann ich mit Aspose.Words für .NET mehrere Signaturzeilen in einem Word-Dokument erstellen und unterzeichnen?

A: Ja, Sie können mit Aspose.Words für .NET mehrere Signaturzeilen in einem Word-Dokument erstellen und unterzeichnen. Jede Signaturzeile kann ihre eigene eindeutige ID und Optionen haben. Sie können die Schritte wiederholen, um weitere Signaturzeilen im Dokument zu erstellen und zu unterzeichnen.

#### F: Kann ich die Signaturzeile nach der Unterzeichnung ändern oder weitere Informationen hinzufügen?

A: Sobald eine Signaturzeile unterzeichnet wurde, wird sie Teil des Dokumentinhalts und kann nicht separat geändert werden. Sie können jedoch nach der unterzeichneten Signaturzeile zusätzliche Informationen oder Inhalte hinzufügen.

#### F: Kann ich die digitale Signatur eines Dokuments überprüfen, das eine Signaturzeile enthält?

 A: Ja, Aspose.Words für .NET bietet Funktionen zum Überprüfen der digitalen Signatur eines Dokuments, das eine Signaturzeile enthält. Sie können die`DigitalSignatureUtil.Verify` Methode zur Überprüfung der Gültigkeit und Authentizität der digitalen Signatur.

#### F: Welches Dateiformat unterstützt Aspose.Words für .NET zum Erstellen und Signieren von Signaturzeilen?

A: Aspose.Words für .NET unterstützt das Erstellen und Signieren von Signaturzeilen im DOCX-Dateiformat. Sie können Signaturzeilen in DOCX-Dateien mit den bereitgestellten Methoden und Klassen erstellen und signieren.