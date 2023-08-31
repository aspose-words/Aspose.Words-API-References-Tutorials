---
title: Legen Sie die Signaturanbieter-ID im Word-Dokument fest
linktitle: Legen Sie die Signaturanbieter-ID im Word-Dokument fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
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


## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET die Signaturanbieter-ID für eine Signaturzeile in einem Word-Dokument festlegt. Wenn Sie die bereitgestellten Schritte befolgen, können Sie das Dokument einfach laden, auf die Signaturzeile zugreifen, die Anbieter-ID festlegen und das Dokument signieren. Die Möglichkeit, die Signaturanbieter-ID festzulegen, hilft dabei, die Identität und Vertrauenswürdigkeit des Unterzeichners festzustellen und erhöht so die Sicherheit und Integrität Ihrer Word-Dokumente. Aspose.Words für .NET bietet eine robuste API für die Textverarbeitung mit digitalen Signaturen, sodass Sie den Signaturprozess problemlos anpassen und verwalten können.

### FAQs zum Festlegen der Signaturanbieter-ID in einem Word-Dokument

#### F: Was ist eine Signaturanbieter-ID in einem Word-Dokument?

A: Eine Signaturanbieter-ID in einem Word-Dokument ist eine eindeutige Kennung, die den Anbieter einer digitalen Signatur angibt. Es hilft dabei, die Entität oder Organisation zu identifizieren, die für die Erstellung und Verwaltung der digitalen Signatur verantwortlich ist.

#### F: Wie kann ich mit Aspose.Words für .NET die Signaturanbieter-ID für eine Signaturzeile in einem Word-Dokument festlegen?

A: Um die Signaturanbieter-ID für eine Signaturzeile in einem Word-Dokument mit Aspose.Words für .NET festzulegen, können Sie die folgenden Schritte ausführen:
1.  Laden Sie das Dokument mit`Document` Klasse und geben Sie den Pfad zur Dokumentdatei an.
2.  Greifen Sie mit der entsprechenden Methode oder Eigenschaft auf die Signaturzeile zu. Sie können zum Beispiel verwenden`GetChild` Methode zum Abrufen der Signaturlinienform.
3. Rufen Sie die Anbieter-ID aus der Signaturzeile ab.
4.  Erstellen Sie eine Instanz von`SignOptions`Klasse und legen Sie die fest`ProviderId` -Eigenschaft zur abgerufenen Anbieter-ID hinzufügen.
5.  Benutzen Sie die`DigitalSignatureUtil.Sign` Methode zum Signieren des Dokuments unter Bereitstellung der erforderlichen Parameter, einschließlich der`SignOptions` Objekt.

#### F: Wie greife ich mit Aspose.Words für .NET auf die Signaturzeile in einem Word-Dokument zu?

 A: Um mit Aspose.Words für .NET auf die Signaturzeile in einem Word-Dokument zuzugreifen, können Sie die entsprechende Methode oder Eigenschaft verwenden, um die Signaturzeilenform aus der Struktur des Dokuments abzurufen. Sie können zum Beispiel die verwenden`GetChild` Methode mit den entsprechenden Parametern, um die gewünschte Signaturlinienform zu erhalten.

#### F: Kann ich die Signaturanbieter-ID für mehrere Signaturzeilen in einem Word-Dokument festlegen?

 A: Ja, Sie können die Signaturanbieter-ID für mehrere Signaturzeilen in einem Word-Dokument festlegen. Sie können die Sammlung von Signaturzeilen im Dokument durchlaufen und mithilfe von die Anbieter-ID für jede Signaturzeile einzeln festlegen`SignOptions.ProviderId` Eigentum.

#### F: Welchen Zweck hat die Signaturanbieter-ID in einem Word-Dokument?

A: Die Signaturanbieter-ID in einem Word-Dokument dient dazu, die Entität oder Organisation zu identifizieren, die für die Erstellung und Verwaltung der digitalen Signatur verantwortlich ist. Es hilft dabei, die Authentizität und Vertrauenswürdigkeit der digitalen Signatur festzustellen, indem es sie einem bestimmten Anbieter zuordnet.

#### F: Welche Arten von digitalen Zertifikaten können zum Festlegen der Signaturanbieter-ID in einem Word-Dokument verwendet werden?

A: Sie können digitale X.509-Zertifikate mit entsprechenden Anbieterinformationen verwenden, um die Signaturanbieter-ID in einem Word-Dokument festzulegen. Das digitale Zertifikat sollte von einer vertrauenswürdigen Zertifizierungsstelle (CA) ausgestellt sein und die notwendigen Metadaten zur Identifizierung des Anbieters enthalten.