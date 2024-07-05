---
title: Festlegen der Signaturanbieter-ID im Word-Dokument
linktitle: Festlegen der Signaturanbieter-ID im Word-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Signaturanbieter-ID in einem Word-Dokument festlegen.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/set-signature-provider-id/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion „Signaturanbieter-ID festlegen“ mit Aspose.Words für .NET. Mit dieser Funktion können Sie die Signaturanbieter-ID für eine Signaturzeile in einem Word-Dokument angeben. Befolgen Sie die folgenden Schritte:

## Schritt 1: Laden des Dokuments und Aufrufen der Signaturzeile

Beginnen Sie mit dem Hochladen des Dokuments mit der Signaturzeile:

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

## Schritt 3: Unterzeichnen des Dokuments

Um das Dokument zu signieren, müssen Sie die Klasse DigitalSignatureUtil verwenden und das Signaturzertifikat angeben:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Achten Sie darauf, die richtigen Pfade für Dokument, Zertifikat und signiertes Dokument anzugeben.

### Beispielquellcode zum Festlegen der Signaturprovider-ID mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Festlegen der Signaturanbieter-ID mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
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

Vervollständigen Sie die Signature Provider-ID in Ihrem Word-Dokument mit Aspose.Words für .NET.


## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Signaturanbieter-ID für eine Signaturzeile in einem Word-Dokument einstellt. Indem Sie die angegebenen Schritte befolgen, können Sie das Dokument problemlos laden, auf die Signaturzeile zugreifen, die Anbieter-ID festlegen und das Dokument unterzeichnen. Die Möglichkeit, die Signaturanbieter-ID festzulegen, hilft dabei, die Identität und Vertrauenswürdigkeit des Unterzeichners festzustellen und so die Sicherheit und Integrität Ihrer Word-Dokumente zu verbessern. Aspose.Words für .NET bietet eine robuste API für die Textverarbeitung mit digitalen Signaturen, sodass Sie den Signaturprozess problemlos anpassen und verwalten können.

### FAQs zum Festlegen der Signaturanbieter-ID im Word-Dokument

#### F: Was ist eine Signaturanbieter-ID in einem Word-Dokument?

A: Eine Signaturanbieter-ID in einem Word-Dokument ist eine eindeutige Kennung, die den Anbieter einer digitalen Signatur angibt. Sie hilft bei der Identifizierung der Entität oder Organisation, die für die Erstellung und Verwaltung der digitalen Signatur verantwortlich ist.

#### F: Wie kann ich mit Aspose.Words für .NET die Signaturanbieter-ID für eine Signaturzeile in einem Word-Dokument festlegen?

A: Um die Signaturanbieter-ID für eine Signaturzeile in einem Word-Dokument mit Aspose.Words für .NET festzulegen, können Sie die folgenden Schritte ausführen:
1.  Laden Sie das Dokument mit dem`Document` Klasse und geben Sie den Pfad zur Dokumentdatei an.
2.  Greifen Sie mit der entsprechenden Methode oder Eigenschaft auf die Signaturzeile zu. Sie können beispielsweise verwenden`GetChild` Methode zum Abrufen der Signaturlinienform.
3. Rufen Sie die Provider-ID aus der Signaturzeile ab.
4.  Erstellen Sie eine Instanz des`SignOptions` Klasse und legen Sie die`ProviderId` -Eigenschaft der abgerufenen Provider-ID.
5.  Verwenden Sie die`DigitalSignatureUtil.Sign` Methode zum Signieren des Dokuments, wobei die erforderlichen Parameter angegeben werden, einschließlich der`SignOptions` Objekt.

#### F: Wie greife ich mit Aspose.Words für .NET auf die Signaturzeile in einem Word-Dokument zu?

 A: Um mit Aspose.Words für .NET auf die Signaturzeile in einem Word-Dokument zuzugreifen, können Sie die entsprechende Methode oder Eigenschaft verwenden, um die Form der Signaturzeile aus der Struktur des Dokuments abzurufen. Sie können beispielsweise die`GetChild` Methode mit den entsprechenden Parametern, um die gewünschte Signaturlinienform zu erhalten.

#### F: Kann ich die Signaturanbieter-ID für mehrere Signaturzeilen in einem Word-Dokument festlegen?

 A: Ja, Sie können die Signaturanbieter-ID für mehrere Signaturzeilen in einem Word-Dokument festlegen. Sie können die Sammlung der Signaturzeilen im Dokument durchlaufen und die Anbieter-ID für jede Signaturzeile einzeln festlegen, indem Sie`SignOptions.ProviderId` Eigentum.

#### F: Was ist der Zweck der Signaturanbieter-ID in einem Word-Dokument?

A: Die Signaturanbieter-ID in einem Word-Dokument dient zur Identifizierung der Entität oder Organisation, die für die Erstellung und Verwaltung der digitalen Signatur verantwortlich ist. Sie hilft dabei, die Authentizität und Vertrauenswürdigkeit der digitalen Signatur festzustellen, indem sie sie einem bestimmten Anbieter zuordnet.

#### F: Welche Art von digitalen Zertifikaten kann zum Festlegen der Signaturanbieter-ID in einem Word-Dokument verwendet werden?

A: Sie können digitale X.509-Zertifikate mit entsprechenden Anbieterinformationen verwenden, um die Signaturanbieter-ID in einem Word-Dokument festzulegen. Das digitale Zertifikat sollte von einer vertrauenswürdigen Zertifizierungsstelle (CA) ausgestellt sein und die erforderlichen Metadaten zur Identifizierung des Anbieters enthalten.