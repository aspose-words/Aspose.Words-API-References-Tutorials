---
title: Få åtkomst till och verifiera signatur
linktitle: Få åtkomst till och verifiera signatur
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du får åtkomst till och verifierar digitala signaturer i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/access-and-verify-signature/
---
den här handledningen guidar vi dig genom stegen för att använda åtkomst- och signaturverifieringsfunktionen i Aspose.Words för .NET. Den här funktionen låter dig komma åt digitala signaturer i ett Word-dokument och verifiera deras giltighet. Följ stegen nedan:

## Steg 1: Ladda dokumentet och komma åt signaturer

Börja med att ladda upp dokumentet som innehåller digitala signaturer:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Steg 2: Bläddra bland digitala signaturer

Använd en loop för att gå igenom alla digitala signaturer i dokumentet:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Få åtkomst till signaturinformation
	Console.WriteLine("*** Signature Found ***");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Den här egenskapen är endast tillgänglig i MS Word-dokument.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Se till att anpassa displaymeddelandena efter dina behov.

### Exempel på källkod för Access And Verify Signature med Aspose.Words för .NET

Här är den fullständiga källkoden för åtkomst och signaturverifiering med Aspose.Words för .NET:

```csharp
	
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("*** Signature Found ***");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Den här egenskapen är endast tillgänglig i MS Word-dokument.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Genom att följa dessa steg kommer du enkelt att kunna komma åt och verifiera de digitala signaturerna i ditt Word-dokument med Aspose.Words för .NET.


