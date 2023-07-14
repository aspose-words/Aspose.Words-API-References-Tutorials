---
title: Vorhandene Signaturzeile im Word-Dokument signieren
linktitle: Vorhandene Signaturzeile im Word-Dokument signieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET eine vorhandene Signaturzeile in einem Word-Dokument signiert. Indem Sie die bereitgestellten Schritte befolgen, können Sie das Dokument einfach laden, auf die vorhandene Signaturzeile zugreifen, die Signaturoptionen festlegen und das Dokument signieren. Die Möglichkeit, eine vorhandene Signaturzeile zu signieren, bietet eine bequeme Möglichkeit, vordefinierten Bereichen in Ihren Word-Dokumenten digitale Signaturen hinzuzufügen und so die Integrität und Authentifizierung des Dokuments sicherzustellen. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit digitalen Signaturen, mit der Sie den Signaturprozess anpassen und die Sicherheit Ihrer Word-Dokumente erhöhen können.

### FAQs

#### F: Was ist eine vorhandene Signaturzeile in einem Word-Dokument?

A: Eine vorhandene Signaturzeile in einem Word-Dokument ist ein vordefinierter Bereich, in dem eine Signatur platziert werden kann. Es wird normalerweise durch eine Form oder ein Objekt im Dokument dargestellt und dient dem Unterzeichner als vorgesehener Bereich zum Hinzufügen seiner digitalen Signatur.

#### F: Wie kann ich mit Aspose.Words für .NET eine vorhandene Signaturzeile in einem Word-Dokument signieren?

A: Um eine vorhandene Signaturzeile in einem Word-Dokument mit Aspose.Words für .NET zu signieren, können Sie die folgenden Schritte ausführen:
1.  Laden Sie das Dokument mit`Document` Klasse und geben Sie den Pfad zur Dokumentdatei an.
2.  Greifen Sie mit der entsprechenden Methode oder Eigenschaft auf die vorhandene Signaturzeile zu. Sie können zum Beispiel verwenden`GetChild` Methode zum Abrufen der Signaturlinienform.
3.  Erstellen Sie eine Instanz von`SignOptions`Klasse und legen Sie die fest`SignatureLineId` Eigenschaft auf die ID der vorhandenen Signaturzeile.
4.  Stellen Sie die ein`SignatureLineImage`Eigentum der`SignOptions` Klasse zum Bild, das die digitale Signatur darstellt.
5.  Laden Sie das Signaturzertifikat mit`CertificateHolder` Klasse und geben Sie das erforderliche Zertifikat und Passwort an.
6.  Benutzen Sie die`DigitalSignatureUtil.Sign` Methode zum Signieren des Dokuments unter Bereitstellung der erforderlichen Parameter, einschließlich der`SignOptions` Objekt.

#### F: Wie greife ich mit Aspose.Words für .NET auf die vorhandene Signaturzeile in einem Word-Dokument zu?

 A: Um mit Aspose.Words für .NET auf die vorhandene Signaturzeile in einem Word-Dokument zuzugreifen, können Sie die entsprechende Methode oder Eigenschaft verwenden, um die Signaturzeilenform aus der Struktur des Dokuments abzurufen. Sie können zum Beispiel die verwenden`GetChild` Methode mit den entsprechenden Parametern, um die gewünschte Signaturlinienform zu erhalten.

#### F: Kann ich das Erscheinungsbild der digitalen Signatur in einer vorhandenen Signaturzeile anpassen?

A: Ja, Sie können das Erscheinungsbild der digitalen Signatur in einer vorhandenen Signaturzeile anpassen, indem Sie eine Bilddatei bereitstellen, die die Signatur darstellt. Das Bild kann ein Logo, eine handschriftliche Unterschrift oder eine andere grafische Darstellung der Unterschrift sein. Sie können das einstellen`SignatureLineImage`Eigentum der`SignOptions` Klasse zu den Bytes der Bilddatei.

#### F: Kann ich in einem Word-Dokument mehrere vorhandene Signaturzeilen signieren?
 A: Ja, Sie können mehrere vorhandene Signaturzeilen in einem Word-Dokument signieren. Sie müssen die Schritte für jede Signaturzeile einzeln befolgen und die entsprechenden Einstellungen vornehmen`SignatureLineId` Und`SignatureLineImage` Werte in der`SignOptions` Objekt für jede Signaturzeile.

#### F: Welches Format sollte die Bilddatei für die digitale Signatur in einer vorhandenen Signaturzeile haben?

 A: Die Bilddatei für die digitale Signatur in einer vorhandenen Signaturzeile kann in verschiedenen Formaten vorliegen, beispielsweise PNG, JPEG, BMP oder GIF. Sie können den Dateipfad angeben oder die Bytes der Bilddatei lesen und sie dem zuordnen`SignatureLineImage`Eigentum der`SignOptions` Klasse.
