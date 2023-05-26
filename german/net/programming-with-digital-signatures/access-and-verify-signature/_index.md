---
title: Auf die Signatur zugreifen und diese überprüfen
linktitle: Auf die Signatur zugreifen und diese überprüfen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET auf digitale Signaturen in einem Word-Dokument zugreifen und diese überprüfen.
type: docs
weight: 10
url: /de/net/programming-with-digital-signatures/access-and-verify-signature/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Zugriffs- und Signaturüberprüfungsfunktion von Aspose.Words für .NET. Mit dieser Funktion können Sie auf digitale Signaturen in einem Word-Dokument zugreifen und deren Gültigkeit überprüfen. Folgen Sie den unteren Schritten:

## Schritt 1: Laden des Dokuments und Zugriff auf Signaturen

Beginnen Sie mit dem Hochladen des Dokuments mit digitalen Signaturen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Schritt 2: Durchsuchen Sie digitale Signaturen

Verwenden Sie eine Schleife, um alle digitalen Signaturen im Dokument zu durchlaufen:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Greifen Sie auf Signaturinformationen zu
	Console.WriteLine("*** Signature Found ***");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Diese Eigenschaft ist nur in MS Word-Dokumenten verfügbar.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Passen Sie die angezeigten Meldungen unbedingt an Ihre Bedürfnisse an.

### Beispielquellcode für Access And Verify Signature mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für den Zugriff und die Signaturüberprüfung mit Aspose.Words für .NET:

```csharp
	
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("*** Signature Found ***");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Diese Eigenschaft ist nur in MS Word-Dokumenten verfügbar.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET problemlos auf die digitalen Signaturen in Ihrem Word-Dokument zugreifen und diese überprüfen.


