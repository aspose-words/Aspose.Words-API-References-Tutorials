---
title: Vorhandene Signaturzeile im Word-Dokument signieren
linktitle: Vorhandene Signaturzeile im Word-Dokument signieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine vorhandene Signaturzeile in einem Word-Dokument signieren.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/signing-existing-signature-line/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Signaturfunktion einer vorhandenen Signaturzeile mit Aspose.Words für .NET. Mit dieser Funktion können Sie eine bereits in einem Word-Dokument vorhandene Signaturzeile digital signieren. Befolgen Sie die folgenden Schritte:

## Schritt 1: Laden des Dokuments und Aufrufen der Signaturzeile

Beginnen Sie mit dem Hochladen des Dokuments mit der vorhandenen Signaturzeile:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Schritt 2: Signaturoptionen festlegen

Erstellen Sie eine Instanz der Klasse SignOptions und legen Sie die Signaturoptionen fest, einschließlich der Signaturzeilen-ID und des Signaturzeilenbilds:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Achten Sie darauf, den richtigen Pfad zum Signaturzeilenbild anzugeben.

## Schritt 3: Laden des Zertifikats

Beginnen Sie mit dem Laden des Signaturzertifikats mithilfe der Klasse CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Achten Sie darauf, den richtigen Pfad zu Ihrem Zertifikat und dem zugehörigen Passwort anzugeben.

## Schritt 4: Vorhandene Signaturzeile unterschreiben

Verwenden Sie die Klasse DigitalSignatureUtil, um die vorhandene Signaturzeile zu signieren:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Achten Sie darauf, die richtigen Pfade für das Quelldokument, das signierte Dokument und das Zertifikat anzugeben.

### Beispielquellcode zum Signieren einer vorhandenen Signaturzeile mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Signieren einer vorhandenen Signaturzeile mit Aspose.Words für .NET:


```csharp

	// Der Pfad zum Dokumentverzeichnis.
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

Indem Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach eine vorhandene Signaturzeile in einem Word-Dokument signieren.

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine vorhandene Signaturzeile in einem Word-Dokument signiert. Indem Sie die angegebenen Schritte befolgen, können Sie das Dokument einfach laden, auf die vorhandene Signaturzeile zugreifen, die Signaturoptionen festlegen und das Dokument signieren. Die Möglichkeit, eine vorhandene Signaturzeile zu signieren, bietet eine bequeme Möglichkeit, digitale Signaturen zu vordefinierten Bereichen in Ihren Word-Dokumenten hinzuzufügen und so die Dokumentintegrität und -authentifizierung sicherzustellen. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit digitalen Signaturen, mit der Sie den Signaturprozess anpassen und die Sicherheit Ihrer Word-Dokumente verbessern können.

### Häufig gestellte Fragen

#### F: Was ist eine vorhandene Signaturzeile in einem Word-Dokument?

A: Eine vorhandene Signaturzeile in einem Word-Dokument ist ein vordefinierter Bereich, in dem eine Signatur platziert werden kann. Sie wird normalerweise durch eine Form oder ein Objekt im Dokument dargestellt und dient dem Unterzeichner als ausgewiesener Platz, um seine digitale Signatur hinzuzufügen.

#### F: Wie kann ich mit Aspose.Words für .NET eine vorhandene Signaturzeile in einem Word-Dokument signieren?

A: Um eine vorhandene Signaturzeile in einem Word-Dokument mit Aspose.Words für .NET zu signieren, können Sie diese Schritte befolgen:
1.  Laden Sie das Dokument mit dem`Document` Klasse und geben Sie den Pfad zur Dokumentdatei an.
2.  Greifen Sie mit der entsprechenden Methode oder Eigenschaft auf die vorhandene Signaturzeile zu. Sie können beispielsweise`GetChild` Methode zum Abrufen der Signaturlinienform.
3.  Erstellen Sie eine Instanz des`SignOptions` Klasse und legen Sie die`SignatureLineId` -Eigenschaft auf die ID der vorhandenen Signaturzeile.
4.  Legen Sie die`SignatureLineImage` Eigentum der`SignOptions` Klasse zum Bild, das die digitale Signatur darstellt.
5.  Laden Sie das Signaturzertifikat mit dem`CertificateHolder` Klasse und geben Sie das erforderliche Zertifikat und Passwort ein.
6.  Verwenden Sie die`DigitalSignatureUtil.Sign` Methode zum Signieren des Dokuments, wobei die erforderlichen Parameter angegeben werden, einschließlich der`SignOptions` Objekt.

#### F: Wie greife ich mit Aspose.Words für .NET auf die vorhandene Signaturzeile in einem Word-Dokument zu?

 A: Um mit Aspose.Words für .NET auf die vorhandene Signaturzeile in einem Word-Dokument zuzugreifen, können Sie die entsprechende Methode oder Eigenschaft verwenden, um die Form der Signaturzeile aus der Struktur des Dokuments abzurufen. Sie können beispielsweise die`GetChild` Methode mit den entsprechenden Parametern, um die gewünschte Signaturlinienform zu erhalten.

#### F: Kann ich das Erscheinungsbild der digitalen Signatur in einer vorhandenen Signaturzeile anpassen?

A: Ja, Sie können das Erscheinungsbild der digitalen Signatur in einer vorhandenen Signaturzeile anpassen, indem Sie eine Bilddatei bereitstellen, die die Signatur darstellt. Das Bild kann ein Logo, eine handschriftliche Unterschrift oder eine andere grafische Darstellung der Signatur sein. Sie können die`SignatureLineImage` Eigentum der`SignOptions` Klasse zu den Bytes der Bilddatei.

#### F: Kann ich mehrere vorhandene Signaturzeilen in einem Word-Dokument unterzeichnen?
 A: Ja, Sie können mehrere vorhandene Signaturzeilen in einem Word-Dokument unterzeichnen. Sie müssen die Schritte für jede Signaturzeile einzeln ausführen und die entsprechenden`SignatureLineId` Und`SignatureLineImage` Werte in der`SignOptions` Objekt für jede Signaturzeile.

#### F: Welches Format sollte die Bilddatei für die digitale Signatur in einer vorhandenen Signaturzeile haben?

 A: Die Bilddatei für die digitale Signatur in einer bestehenden Signaturzeile kann in verschiedenen Formaten vorliegen, wie etwa PNG, JPEG, BMP oder GIF. Sie können den Dateipfad angeben oder die Bytes der Bilddatei auslesen und diese dem`SignatureLineImage` Eigentum der`SignOptions` Klasse.
