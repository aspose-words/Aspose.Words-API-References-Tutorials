---
title: Lösenordsskydd
linktitle: Lösenordsskydd
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du lösenordsskyddar dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-protection/password-protection/
---

den här handledningen guidar vi dig genom stegen för att använda lösenordsskyddsfunktionen i Aspose.Words för .NET. Denna funktion låter dig skydda ett Word-dokument med ett lösenord för att säkerställa dess konfidentialitet. Följ stegen nedan:

## Steg 1: Skapa dokumentet och tillämpa skydd

Börja med att skapa en instans av klassen Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Steg 2: Använd lösenordsskydd

Sedan kan du tillämpa lösenordsskydd med hjälp av Document-objektets Protect()-metod:

```csharp
doc.Protect(ProtectionType.NoProtection, "password");
```

Se till att ersätta "lösenord" med det faktiska lösenordet du vill använda för att skydda dokumentet.

## Steg 3: Spara det skyddade dokumentet

Slutligen kan du spara det skyddade dokumentet med hjälp av metoden Save() för Document-objektet:

```csharp
doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");
```

Var noga med att ange rätt sökväg och filnamn för att spara det skyddade dokumentet.

### Exempel på källkod för lösenordsskydd med Aspose.Words för .NET

Här är den fullständiga källkoden för lösenordsskydd med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	//Tillämpa dokumentskydd.
	doc.Protect(ProtectionType.NoProtection, "password");

	doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");

```

Kom ihåg att ersätta "DIN DOKUMENTKABEL" med katalogen för dina dokument och "lösenord" med det faktiska lösenordet du vill använda.

