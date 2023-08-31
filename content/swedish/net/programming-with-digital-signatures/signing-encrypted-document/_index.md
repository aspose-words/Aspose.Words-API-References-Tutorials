---
title: Signering av krypterade Word-dokument
linktitle: Signering av krypterade Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du digitalt signerar ett krypterat Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/signing-encrypted-document/
---
den här handledningen kommer vi att guida dig genom stegen för att använda funktionen för att signera ett krypterat Word-dokument med Aspose.Words för .NET. Med den här funktionen kan du digitalt signera ett Word-dokument som är krypterat med ett dekrypteringslösenord. Följ stegen nedan:

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

## Slutsats

I den här handledningen utforskade vi processen att signera ett krypterat Word-dokument med Aspose.Words för .NET. Genom att tillhandahålla dekrypteringslösenordet och signeringscertifikatet kan vi lägga till en digital signatur till ett krypterat dokument. Att signera krypterade dokument säkerställer deras autenticitet och integritet, vilket ger ett extra lager av säkerhet. Aspose.Words för .NET låter dig signera krypterade dokument och upprätthålla säkerheten och pålitligheten för dina Word-filer.

### FAQ's

#### F: Vad är dokumentsignering i Aspose.Words för .NET?

S: Dokumentsignering i Aspose.Words för .NET hänvisar till processen att digitalt signera ett Word-dokument för att säkerställa dess äkthet, integritet och icke-avvisande. Det innebär att lägga till en digital signatur till dokumentet med hjälp av ett certifikat.

#### F: Vad är ett krypterat Word-dokument?

S: Ett krypterat Word-dokument är ett dokument som har krypterats med ett lösenord. Kryptering är en säkerhetsåtgärd som skyddar innehållet i dokumentet genom att förvränga det och göra det oläsligt utan korrekt dekrypteringslösenord.

#### F: Hur kan jag signera ett krypterat Word-dokument med Aspose.Words för .NET?

S: För att signera ett krypterat Word-dokument med Aspose.Words för .NET måste du ange dekrypteringslösenordet tillsammans med signeringscertifikatet. Följ dessa steg:
1.  Ställ in dekrypteringslösenordet i`SignOptions` objekt.
2.  Ladda signeringscertifikatet med hjälp av`CertificateHolder` klass.
3.  Använd`DigitalSignatureUtil.Sign` metod för att signera det krypterade dokumentet, tillhandahålla nödvändiga parametrar.

#### F: Vad är syftet med att signera ett krypterat dokument?

S: Genom att signera ett krypterat dokument med Aspose.Words för .NET kan du lägga till en digital signatur till dokumentet även när det är krypterat. Detta ger ett extra lager av säkerhet och säkerställer äktheten och integriteten hos det krypterade innehållet. Det låter mottagarna verifiera dokumentets ursprung och upptäcka eventuella manipulationer.

#### F: Kan jag signera ett krypterat dokument utan att ange dekrypteringslösenordet?

S: Nej, för att signera ett krypterat dokument måste du ange rätt dekrypteringslösenord. Dekrypteringslösenordet krävs för att komma åt och ändra det krypterade innehållet i dokumentet innan den digitala signaturen tillämpas.

#### F: Kan jag signera ett krypterat Word-dokument med vilket certifikat som helst?

S: För att signera ett krypterat Word-dokument med Aspose.Words för .NET behöver du ett giltigt X.509-certifikat. Certifikatet kan erhållas från en betrodd certifikatutfärdare (CA) eller så kan ett självsignerat certifikat användas för teständamål.

#### F: Kan jag signera flera krypterade Word-dokument med samma certifikat?

 S: Ja, du kan signera flera krypterade Word-dokument med samma certifikat. När du har laddat certifikatet med hjälp av`CertificateHolder` klass, kan du återanvända den för att signera flera krypterade dokument.

#### F: Kan jag verifiera den digitala signaturen för ett signerat krypterat dokument?

 S: Ja, Aspose.Words för .NET tillhandahåller funktionalitet för att verifiera den digitala signaturen för ett signerat krypterat dokument. Du kan använda`DigitalSignatureUtil.Verify` metod för att kontrollera giltigheten och äktheten av den digitala signaturen.

#### F: Vilket filformat stöder Aspose.Words for .NET för att signera krypterade dokument?

 S: Aspose.Words för .NET stöder signering av krypterade Word-dokument i filformatet DOCX. Du kan signera krypterade DOCX-filer med hjälp av`DigitalSignatureUtil.Sign` metod tillsammans med det nödvändiga dekrypteringslösenordet och certifikatet.

#### F: Hur påverkar krypteringen att signera ett krypterat dokument?

S: Att signera ett krypterat dokument med Aspose.Words för .NET påverkar inte krypteringen av dokumentet. Krypteringen förblir intakt och den digitala signaturen läggs till det krypterade innehållet. Den digitala signaturen ger ytterligare säkerhet och verifiering utan att kompromissa med krypteringen som tillämpas på dokumentet.