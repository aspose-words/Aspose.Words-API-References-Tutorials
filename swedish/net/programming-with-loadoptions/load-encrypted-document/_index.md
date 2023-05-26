---
title: Ladda krypterade dokument
linktitle: Ladda krypterade dokument
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du laddar och sparar krypterade dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-loadoptions/load-encrypted-document/
---

När man arbetar med krypterade dokument i en C#-applikation är det viktigt att kunna ladda dem korrekt genom att ange rätt lösenord. Med Aspose.Words-biblioteket för .NET kan du enkelt ladda krypterade dokument med lämpliga laddningsalternativ. I den här steg-för-steg-guiden visar vi dig hur du använder C#-källkoden för Aspose.Words för .NET för att ladda ett krypterat dokument med LoadOptions laddningsalternativ.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett kraftfullt bibliotek för att skapa, redigera, konvertera och skydda Word-dokument på olika plattformar inklusive .NET. Den erbjuder många funktioner för att manipulera dokument, som att infoga text, ändra formatering, lägga till avsnitt och mycket mer.

## Laddar ett krypterat dokument

Det första steget är att ladda upp ett krypterat dokument med lämpliga uppladdningsalternativ. I vårt fall använder vi klassen Document för att ladda dokumentet genom att ange dokumentets sökväg och lösenord. Här är ett exempel :

```csharp
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));
```

I det här exemplet laddar vi dokumentet "Encrypted.docx" som finns i dokumentkatalogen med lösenordet "lösenord".

## Sparar ett krypterat dokument

Efter att ha laddat upp ett krypterat dokument kan du också spara det genom att ange ett nytt lösenord för utdatafilen. I vårt exempel använder vi klassen OdtSaveOptions för att spara dokumentet i ODT-format med ett nytt lösenord. Så här gör du:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

I det här exemplet sparar vi dokumentet med namnet "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt" genom att ange det nya lösenordet "newpassword".

### Exempel på källkod för LoadOptions med "Load Encrypted Document" funktionalitet med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda ett krypterat dokument med det angivna lösenordet
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));

//Spara ett krypterat dokument med ett nytt lösenord
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

## Slutsats

I den här guiden förklarade vi hur man laddar och sparar krypterade dokument med Aspose.Words-biblioteket för .NET. Genom att följa de medföljande stegen och använda den medföljande C#-källkoden kan du enkelt tillämpa den här funktionen i din C#-applikation. Att ladda upp krypterade dokument håller din data säker och låter dig arbeta med skyddade dokument i Aspose.Words.