---
title: Erstellen Sie eine neue Signaturzeile und legen Sie die Anbieter-ID fest
linktitle: Erstellen Sie eine neue Signaturzeile und legen Sie die Anbieter-ID fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

## Abschluss

In diesem Tutorial haben wir die Funktion zum Erstellen einer neuen Signaturzeile und zum Festlegen der Anbieter-ID in einem Word-Dokument mit Aspose.Words für .NET untersucht. Wenn Sie die bereitgestellten Schritte befolgen, können Sie ganz einfach eine Signaturzeile mit benutzerdefinierten Optionen einfügen und diese mithilfe der Anbieter-ID einem bestimmten Anbieter zuordnen. Das Hinzufügen von Signaturzeilen und die Anpassung der Anbieterinformationen erhöhen die Authentizität und Vertrauenswürdigkeit Ihrer Dokumente. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Signaturzeilen und digitalen Zertifikaten in Word-Dokumenten, sodass Sie den Signaturprozess automatisieren und die Gültigkeit Ihrer Dokumente sicherstellen können.

### FAQs

#### F: Was ist eine Anbieter-ID in einer Signaturzeile?

A: Eine Anbieter-ID in einer Signaturzeile ist eine eindeutige Kennung, die den Anbieter der digitalen Signatur darstellt. Es hilft dabei, die Quelle oder Organisation zu identifizieren, die für die Signatur verantwortlich ist.

#### F: Wie kann ich mit Aspose.Words für .NET eine neue Signaturzeile in einem Word-Dokument erstellen?

A: Um mit Aspose.Words für .NET eine neue Signaturzeile in einem Word-Dokument zu erstellen, können Sie die folgenden Schritte ausführen:
1.  Erstellen Sie eine Instanz von`Document` Klasse und a`DocumentBuilder` Objekt.
2.  Erstellen Sie eine Instanz von`SignatureLineOptions` Klasse und legen Sie die gewünschten Signaturzeilenoptionen fest.
3.  Benutzen Sie die`InsertSignatureLine` Methode der`DocumentBuilder` Objekt, um die Signaturzeile in das Dokument einzufügen.

#### F: Kann ich die Optionen der Signaturzeile anpassen, z. B. Name, Titel und Anweisungen des Unterzeichners?

 A: Ja, Sie können die Optionen der Signaturzeile anpassen. Der`SignatureLineOptions` Die Klasse stellt Eigenschaften bereit, um die gewünschten Optionen festzulegen, z`Signer`, `SignerTitle`, `Instructions`, `AllowComments`usw. Sie können diese Eigenschaften ändern, bevor Sie die Signaturzeile einfügen.

#### F: Wozu dient das Festlegen der Provider-ID für eine Signaturzeile?

A: Das Festlegen der Anbieter-ID für eine Signaturzeile hilft dabei, die Quelle oder Organisation zu identifizieren, die für die digitale Signatur verantwortlich ist. Es ermöglicht Ihnen, die Signatur einem bestimmten Anbieter oder einer bestimmten Entität zuzuordnen und liefert so zusätzliche Informationen über den Ursprung und die Vertrauenswürdigkeit der Signatur.

#### F: Wie kann ich mit Aspose.Words für .NET die Anbieter-ID für eine Signaturzeile festlegen?

A: Um die Anbieter-ID für eine Signaturzeile mithilfe von Aspose.Words für .NET festzulegen, können Sie die folgenden Schritte ausführen:
1.  Nachdem Sie die Signaturzeile eingefügt haben, greifen Sie auf zu`ProviderId` Eigentum der`SignatureLine` Objekt.
2.  Stellen Sie die ein`ProviderId` Eigenschaft mit dem gewünschten Anbieter-ID-Wert`Guid` Datentyp.

#### F: Kann ich das Dokument signieren, nachdem ich eine neue Signaturzeile erstellt und die Anbieter-ID festgelegt habe?

 A: Ja, nachdem Sie eine neue Signaturzeile erstellt und die Anbieter-ID festgelegt haben, können Sie das Dokument signieren. Um das Dokument zu signieren, müssen Sie die Signaturoptionen festlegen, einschließlich der Signaturzeilen-ID, der Anbieter-ID, Kommentare und der Signaturzeit. Dann verwenden Sie die`DigitalSignatureUtil.Sign` Methode zum Signieren des Dokuments mit einem digitalen Zertifikat.

#### F: Kann ich für jede Signaturzeile in einem Word-Dokument eine bestimmte Anbieter-ID angeben?

A: Ja, Sie können für jede Signaturzeile in einem Word-Dokument eine bestimmte Anbieter-ID angeben. Nachdem Sie jede Signaturzeile eingefügt haben, können Sie die Anbieter-ID für diese bestimmte Signaturzeile festlegen, indem Sie auf zugreifen`ProviderId` Eigentum des jeweiligen`SignatureLine` Objekt.

#### F: Wie kann ich das geänderte Dokument speichern, nachdem ich eine neue Signaturzeile erstellt und die Anbieter-ID festgelegt habe?

 A: Um das geänderte Dokument nach dem Erstellen einer neuen Signaturzeile und dem Festlegen der Anbieter-ID zu speichern, können Sie die verwenden`Save` Methode der`Document` Objekt. Geben Sie den richtigen Pfad und Dateinamen an, um das Dokument zu speichern.

#### F: Welches Dateiformat unterstützt Aspose.Words für .NET zum Erstellen und Signieren von Signaturzeilen?

A: Aspose.Words für .NET unterstützt das Erstellen und Signieren von Signaturzeilen im DOCX-Dateiformat. Mit den bereitgestellten Methoden und Klassen können Sie Signaturzeilen in DOCX-Dateien erstellen und signieren.

#### F: Kann ich die Anbieter-ID oder andere Optionen einer Signaturzeile ändern, nachdem diese signiert wurde?

A: Sobald eine Signaturzeile signiert wurde, wird sie Teil des Dokumentinhalts und kann nicht separat geändert werden. Alle Änderungen an der Signaturzeile, wie z. B. die Änderung der Anbieter-ID oder anderer Optionen, würden das Entfernen der vorhandenen Signatur und das Erstellen einer neuen Signaturzeile erfordern.