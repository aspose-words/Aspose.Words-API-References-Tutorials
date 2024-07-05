---
title: Neue Signaturzeile erstellen und Provider-ID festlegen
linktitle: Neue Signaturzeile erstellen und Provider-ID festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine neue Signaturzeile erstellen und die Anbieter-ID in einem Word-Dokument festlegen.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Funktion „Neue Signaturzeile erstellen und Anbieter-ID festlegen“ mit Aspose.Words für .NET. Mit dieser Funktion können Sie eine Signaturzeile in ein Word-Dokument einfügen, benutzerdefinierte Optionen festlegen und das Dokument signieren. Befolgen Sie die folgenden Schritte:

## Schritt 1: Erstellen des Dokuments und des Generators

Beginnen Sie mit der Erstellung einer Instanz der Document-Klasse und eines DocumentBuilder-Objekts:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Festlegen der Signaturzeilenoptionen

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

## Schritt 4: Provider-ID festlegen

Legen Sie die Provider-ID für die Signaturzeile mithilfe der ProviderId-Eigenschaft fest:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Achten Sie darauf, die richtige Provider-ID für Ihren Anwendungsfall anzugeben.

## Schritt 5: Speichern Sie das Dokument

Speichern Sie das geänderte Dokument:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Geben Sie zum Speichern des Dokuments unbedingt den richtigen Pfad und Dateinamen an.

## Schritt 6: Unterzeichnen des Dokuments

Um das Dokument zu signieren, müssen Sie die Signaturoptionen festlegen und die Klasse DigitalSignatureUtil verwenden:

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

Achten Sie darauf, die richtigen Pfade für Dokument, Zertifikat und signiertes Dokument anzugeben.

### Beispielquellcode zum Erstellen einer neuen Signaturzeile und Festlegen der Provider-ID mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Erstellen einer neuen Signaturzeile und Festlegen der Provider-ID mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
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

Indem Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET ganz einfach eine neue Signaturzeile erstellen und die Anbieter-ID in Ihrem Word-Dokument festlegen.

## Abschluss

In diesem Tutorial haben wir die Funktion zum Erstellen einer neuen Signaturzeile und Festlegen der Anbieter-ID in einem Word-Dokument mithilfe von Aspose.Words für .NET untersucht. Indem Sie die angegebenen Schritte befolgen, können Sie problemlos eine Signaturzeile mit benutzerdefinierten Optionen einfügen und sie mithilfe der Anbieter-ID einem bestimmten Anbieter zuordnen. Das Hinzufügen von Signaturzeilen und Anpassen der Anbieterinformationen erhöht die Authentizität und Vertrauenswürdigkeit Ihrer Dokumente. Aspose.Words für .NET bietet eine leistungsstarke API für die Textverarbeitung mit Signaturzeilen und digitalen Zertifikaten in Word-Dokumenten, mit der Sie den Signaturprozess automatisieren und die Gültigkeit Ihrer Dokumente sicherstellen können.

### Häufig gestellte Fragen

#### F: Was ist eine Anbieter-ID in einer Signaturzeile?

A: Eine Anbieter-ID in einer Signaturzeile ist eine eindeutige Kennung, die den Anbieter der digitalen Signatur darstellt. Sie hilft bei der Identifizierung der Quelle oder Organisation, die für die Signatur verantwortlich ist.

#### F: Wie kann ich mit Aspose.Words für .NET eine neue Signaturzeile in einem Word-Dokument erstellen?

A: Um mit Aspose.Words für .NET eine neue Signaturzeile in einem Word-Dokument zu erstellen, können Sie diese Schritte befolgen:
1.  Erstellen Sie eine Instanz des`Document` Klasse und eine`DocumentBuilder` Objekt.
2.  Erstellen Sie eine Instanz des`SignatureLineOptions` Klasse und legen Sie die gewünschten Signaturzeilenoptionen fest.
3.  Verwenden Sie die`InsertSignatureLine` Methode der`DocumentBuilder` Objekt, um die Signaturzeile in das Dokument einzufügen.

#### F: Kann ich die Optionen der Signaturzeile, beispielsweise Name des Unterzeichners, Titel und Anweisungen, anpassen?

 A: Ja, Sie können die Optionen der Signaturzeile anpassen. Die`SignatureLineOptions` Klasse bietet Eigenschaften zum Setzen der gewünschten Optionen, wie zum Beispiel`Signer`, `SignerTitle`, `Instructions`, `AllowComments`usw. Sie können diese Eigenschaften ändern, bevor Sie die Signaturzeile einfügen.

#### F: Welchen Zweck hat das Festlegen der Anbieter-ID für eine Signaturzeile?

A: Durch das Festlegen der Anbieter-ID für eine Signaturzeile können Sie die Quelle oder Organisation identifizieren, die für die digitale Signatur verantwortlich ist. Sie können die Signatur einem bestimmten Anbieter oder einer bestimmten Entität zuordnen und erhalten so zusätzliche Informationen über den Ursprung und die Vertrauenswürdigkeit der Signatur.

#### F: Wie kann ich mit Aspose.Words für .NET die Anbieter-ID für eine Signaturzeile festlegen?

A: Um die Anbieter-ID für eine Signaturzeile mit Aspose.Words für .NET festzulegen, können Sie die folgenden Schritte ausführen:
1.  Nach dem Einfügen der Signaturzeile gelangen Sie zum`ProviderId` Eigentum der`SignatureLine` Objekt.
2.  Legen Sie die`ProviderId` -Eigenschaft auf den gewünschten Provider-ID-Wert mithilfe der`Guid` Datentyp.

#### F: Kann ich das Dokument unterzeichnen, nachdem ich eine neue Signaturzeile erstellt und die Anbieter-ID festgelegt habe?

 A: Ja, nachdem Sie eine neue Signaturzeile erstellt und die Anbieter-ID festgelegt haben, können Sie das Dokument signieren. Um das Dokument zu signieren, müssen Sie die Signaturoptionen festlegen, einschließlich der Signaturzeilen-ID, der Anbieter-ID, der Kommentare und der Signaturzeit. Verwenden Sie dann die`DigitalSignatureUtil.Sign` Methode zum Signieren des Dokuments mit einem digitalen Zertifikat.

#### F: Kann ich für jede Signaturzeile in einem Word-Dokument eine bestimmte Anbieter-ID angeben?

A: Ja, Sie können für jede Signaturzeile in einem Word-Dokument eine bestimmte Anbieter-ID angeben. Nachdem Sie jede Signaturzeile eingefügt haben, können Sie die Anbieter-ID für diese bestimmte Signaturzeile festlegen, indem Sie auf das`ProviderId` Eigentum der jeweiligen`SignatureLine` Objekt.

#### F: Wie kann ich das geänderte Dokument speichern, nachdem ich eine neue Signaturzeile erstellt und die Anbieter-ID festgelegt habe?

 A: Um das geänderte Dokument nach dem Erstellen einer neuen Signaturzeile und dem Festlegen der Anbieter-ID zu speichern, können Sie das`Save` Methode der`Document` Objekt. Geben Sie den richtigen Pfad und Dateinamen zum Speichern des Dokuments an.

#### F: Welches Dateiformat unterstützt Aspose.Words für .NET zum Erstellen und Signieren von Signaturzeilen?

A: Aspose.Words für .NET unterstützt das Erstellen und Signieren von Signaturzeilen im DOCX-Dateiformat. Sie können Signaturzeilen in DOCX-Dateien mit den bereitgestellten Methoden und Klassen erstellen und signieren.

#### F: Kann ich die Anbieter-ID oder andere Optionen einer Signaturzeile nach der Unterzeichnung ändern?

A: Sobald eine Signaturzeile unterzeichnet wurde, wird sie Teil des Dokumentinhalts und kann nicht separat geändert werden. Alle Änderungen an der Signaturzeile, wie z. B. das Ändern der Anbieter-ID oder anderer Optionen, erfordern das Entfernen der vorhandenen Signatur und das Erstellen einer neuen Signaturzeile.