---
title: Signering av krypterade dokument
linktitle: Signering av krypterade dokument
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du digitalt signerar ett krypterat dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/signing-encrypted-document/
---

I den här handledningen kommer vi att guida dig genom stegen för att använda funktionen för att signera ett krypterat dokument med Aspose.Words för .NET. Med den här funktionen kan du digitalt signera ett Word-dokument som är krypterat med ett dekrypteringslösenord. Följ stegen nedan:

## Steg 1: Ställ in signaturalternativ

Skapa en instans av klassen SignOptions och ställ in dekrypteringslösenordet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Var noga med att ange rätt dekrypteringslösenord för ditt krypterade dokument.

## Steg 2: Laddar certifikatet

Börja med att ladda signeringscertifikatet med klassen CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Var noga med att ange rätt sökväg till ditt certifikat och tillhörande lösenord.

## Steg 3: Signera det krypterade dokumentet

Använd klassen DigitalSignatureUtil för att signera det krypterade dokumentet:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Se till att ange rätt sökvägar för det krypterade dokumentet, det signerade dokumentet och certifikatet.

### Exempel på källkod för att signera krypterade dokument med Aspose.Words för .NET

Här är den fullständiga källkoden för att signera ett krypterat dokument med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Genom att följa dessa steg kan du enkelt signera ett krypterat Word-dokument med Aspose.Words för .NET.

