---
title: Lässkydd i Word-dokument
linktitle: Lässkydd i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skyddar dina skrivskyddade i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-protection/read-only-protection/
---
den här handledningen guidar vi dig genom stegen för att använda skrivskyddsfunktionen i Aspose.Words för .NET. Med den här funktionen kan du göra ett Word-dokument skrivskyddat för att förhindra obehörig ändring. Följ stegen nedan:

## Steg 1: Skapa dokumentet och tillämpa skydd

Börja med att skapa en instans av klassen Document och ett DocumentBuilder-objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Skriv innehåll till dokumentet
Använd DocumentBuilder-objektet för att skriva innehåll till dokumentet:

```csharp
builder.Write("Open document as read-only");
```

## Steg 3: Ange lösenord och gör dokumentet skrivskyddat

Ställ in ett lösenord för dokumentet med egenskapen SetPassword() för WriteProtection-objektet:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Se till att ersätta "Mitt lösenord" med det faktiska lösenord du vill använda.

## Steg 4: Använd skrivskyddat dokument

Gör dokumentet skrivskyddat genom att ställa in egenskapen ReadOnlyRecommended till true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Steg 5: Använd skrivskyddat och spara dokumentet

Till sist, tillämpa skrivskyddat med metoden Protect() för Document-objektet:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Var noga med att ange rätt sökväg och filnamn för att spara det skyddade dokumentet.

### Exempel på källkod för skrivskyddad användning av Aspose.Words för .NET

Här är den fullständiga källkoden för skrivskyddat skydd med Aspose.Words för .NET:

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Ange ett lösenord som är upp till 15 tecken långt.
doc.WriteProtection.SetPassword("MyPassword");

// Gör dokumentet som skrivskyddat.
doc.WriteProtection.ReadOnlyRecommended = true;

// Använd skrivskydd som skrivskyddat.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Genom att följa dessa steg kan du enkelt skydda dina dokument

## Slutsats

I den här handledningen utforskade vi skrivskyddsfunktionen i Aspose.Words för .NET, som låter dig göra Word-dokument skrivskyddade för att förhindra obehöriga ändringar. Genom att följa de medföljande stegen kan du enkelt tillämpa skrivskydd på dina dokument och förbättra deras säkerhet. Skrivskyddat hjälper till att säkerställa integriteten och noggrannheten hos ditt dokuments innehåll genom att begränsa redigeringsmöjligheterna. Aspose.Words för .NET tillhandahåller ett kraftfullt och flexibelt API för att hantera dokumentskydd och stöder olika andra funktioner för att anpassa och säkra dina Word-dokument.

### Vanliga frågor för skrivskydd i word-dokument

#### F: Vad är skrivskydd i Aspose.Words för .NET?

S: Skrivskyddat i Aspose.Words för .NET är en funktion som låter dig göra ett Word-dokument skrivskyddat, vilket förhindrar obehöriga ändringar. När ett dokument är inställt på skrivskyddat kan användare öppna och visa dokumentet, men de kan inte göra några ändringar i dess innehåll.

#### F: Hur kan jag tillämpa skrivskydd på ett Word-dokument med Aspose.Words för .NET?

S: För att tillämpa skrivskyddat skydd på ett Word-dokument med Aspose.Words för .NET, kan du följa dessa steg:
1.  Skapa en instans av`Document` klass och a`DocumentBuilder` objekt.
2.  Använd`DocumentBuilder` att skriva innehåll till dokumentet.
3.  Ställ in ett lösenord för dokumentet med hjälp av`SetPassword` metod för`WriteProtection` objekt.
4.  Ställ in`ReadOnlyRecommended`egendom av`WriteProtection` invända mot`true` att rekommendera att du öppnar dokumentet som skrivskyddat.
5.  Tillämpa skrivskyddat med hjälp av`Protect` metod för`Document` objekt, som anger`ProtectionType` som`ReadOnly`.
6.  Spara det skyddade dokumentet med hjälp av`Save` metod för`Document` objekt.

#### F: Kan jag ta bort skrivskyddet från ett Word-dokument med Aspose.Words för .NET?

S: Ja, du kan ta bort skrivskyddet från ett Word-dokument med Aspose.Words för .NET. För att göra detta kan du använda`Unprotect` metod för`Document` klass, vilket tar bort alla befintliga skydd från dokumentet.

#### F: Kan jag ställa in ett annat lösenord för skrivskydd i ett Word-dokument?

 S: Nej, skrivskyddet i Aspose.Words för .NET tillåter dig inte att ange ett separat lösenord specifikt för skrivskydd. Lösenordet som ställts in med hjälp av`SetPassword` metod för`WriteProtection` objekt gäller det övergripande dokumentskyddet, inklusive både lässkydd och läs-skrivskydd.

#### F: Kan användare kringgå skrivskyddet i ett Word-dokument?

S: Lässkydd i ett Word-dokument är avsett att motverka och förhindra oavsiktliga eller obehöriga ändringar. Även om det ger en skyddsnivå kan det kringgås av användare med tillräcklig teknisk kunskap eller redigeringsbehörighet. Men skrivskyddet fungerar som ett avskräckande och hjälper till att upprätthålla dokumentets integritet.