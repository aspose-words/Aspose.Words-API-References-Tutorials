---
title: Kryptera dokument med lösenord
linktitle: Kryptera dokument med lösenord
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du krypterar dokument med ett lösenord med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
Dokumentsäkerhet är viktigt när du arbetar med filer i en C#-applikation. Med Aspose.Words-biblioteket för .NET kan du enkelt skydda dina dokument genom att kryptera dem med ett lösenord. I den här steg-för-steg-guiden går vi igenom hur du använder Aspose.Words för .NET C#-källkod för att kryptera ett dokument med hjälp av DocSaveOptions-sparalternativen.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett kraftfullt bibliotek för att skapa, redigera, konvertera och skydda Word-dokument på olika plattformar inklusive .NET. Den erbjuder många funktioner för att manipulera dokument, som att infoga text, ändra formatering, lägga till avsnitt och mycket mer.

## Steg 1: Definiera dokumentkatalogen

Det första steget är att ställa in katalogen där du vill spara det krypterade dokumentet. Du måste ange den fullständiga katalogsökvägen. Till exempel :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: Skapa och redigera ett dokument

Sedan kan du skapa ett dokument och lägga till innehåll till det. Använd klassen DocumentBuilder från Aspose.Words för att bygga innehållet i ditt dokument. Till exempel :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

I det här exemplet skapar vi ett nytt tomt dokument och använder sedan DocumentBuilder för att skriva texten "Hello World!".

## Steg 3: Konfigurera inspelningsalternativ

Låt oss nu konfigurera sparalternativen för vårt dokument. Använd klassen DocSaveOptions för att ange sparinställningar. Till exempel :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

I det här exemplet skapar vi ett nytt DocSaveOptions-objekt och ställer in lösenordsegenskapen till "lösenord" för att kryptera dokumentet med detta lösenord.

## Steg 4: Aktivera funktionen "Kryptera dokument med lösenord".

Vi har redan konfigurerat alternativen för

registrering med det angivna lösenordet, vilket automatiskt aktiverar funktionen "Kryptera dokument med lösenord". Detta säkerställer att dokumentet krypteras med det lösenord som angavs när det sparades.

## Steg 5: Spara dokumentet

Slutligen kan du spara dokumentet med hjälp av Spara-metoden för klassen Document. Ange den fullständiga sökvägen till filen och önskat filnamn. Till exempel :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Se till att ersätta "dataDir" med katalogsökvägen till dina dokument.

### Exempel på källkod för DocSaveOptions spara alternativ med "Kryptera dokument med lösenord" funktionalitet med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa och redigera ett dokument
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Konfigurera sparalternativ med funktionen "Kryptera dokument med lösenord".
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Spara dokumentet med de angivna alternativen
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Slutsats

I den här guiden förklarade vi hur man använder Aspose.Words-biblioteket för .NET för att kryptera ett dokument med ett lösenord med hjälp av DocSaveOptions-sparalternativen. Genom att följa de medföljande stegen och använda den medföljande C#-källkoden kan du enkelt tillämpa den här funktionen i din C#-applikation. Att kryptera dokumentet med ett lösenord garanterar dess konfidentialitet och säkerhet vid hanteringen.