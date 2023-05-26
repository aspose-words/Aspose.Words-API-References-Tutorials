---
title: Signera dokument
linktitle: Signera dokument
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du digitalt signerar ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/sign-document/
---

I den här handledningen går vi igenom stegen för att använda dokumentsigneringsfunktionen med Aspose.Words för .NET. Den här funktionen låter dig signera ett Word-dokument digitalt med ett certifikat. Följ stegen nedan:

## Steg 1: Laddar certifikatet

Börja med att ladda signeringscertifikatet med klassen CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Var noga med att ange rätt sökväg till ditt certifikat och tillhörande lösenord.

## Steg 2: Signera dokumentet

Använd klassen DigitalSignatureUtil för att signera dokumentet:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Var noga med att ange rätt sökvägar för källdokumentet och det signerade dokumentet.

### Exempel på källkod för Sign Document med Aspose.Words för .NET

Här är den fullständiga källkoden för att signera ett dokument med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Genom att följa dessa steg kan du enkelt signera ett Word-dokument med Aspose.Words för .NET.



