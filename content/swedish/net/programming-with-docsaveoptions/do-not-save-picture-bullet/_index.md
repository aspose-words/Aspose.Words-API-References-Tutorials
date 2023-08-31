---
title: Spara inte Picture Bullet
linktitle: Spara inte Picture Bullet
second_title: Aspose.Words Document Processing API
description: Lär dig hur du inaktiverar att spara bildpunkter i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Bildpunkter är en vanlig funktion i Word-dokument för att lägga till anpassade punkter. I vissa fall kan det dock vara nödvändigt att inaktivera registrering av bildpunkter när du manipulerar dokument med Aspose.Words Library för .NET. I denna steg-för-steg-guide kommer vi att förklara hur man använder Aspose.Words C#-källkod för .NET för att inaktivera lagring av bildpunkter med hjälp av DocSaveOptions-sparalternativ.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett kraftfullt bibliotek för att skapa, redigera, konvertera och skydda Word-dokument på olika plattformar inklusive .NET. Den erbjuder många funktioner för att manipulera dokument, som att infoga text, ändra formatering, lägga till avsnitt och mycket mer.

## Steg 1: Ställa in dokumentkatalogen

Det första steget är att definiera katalogen där dina dokument finns. Du måste ange den fullständiga katalogsökvägen. Till exempel :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: Ladda dokumentet med bildpunkter

Därefter måste du ladda dokumentet med bildpunkter. Använd klassen Document för att ladda dokumentet från en fil. Till exempel :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

I det här exemplet laddar vi dokumentet från filen "Image bullet points.docx"

  finns i dokumentkatalogen.

## Steg 3: Konfigurera inspelningsalternativ

Låt oss nu konfigurera sparalternativen för vårt dokument. Använd klassen DocSaveOptions för att ange sparinställningar. Till exempel :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

det här exemplet skapar vi ett nytt DocSaveOptions-objekt och ställer in egenskapen SavePictureBullet till false för att inaktivera lagring av bildpunkter.

## Steg 4: Aktivera funktionen "Spara inte bildpunkten".

För att aktivera funktionen "Spara inte Picture Bullet" har vi redan konfigurerat sparalternativen med SavePictureBullet inställt på false. Detta säkerställer att bildpunkter inte sparas i slutdokumentet.

## Steg 5: Spara dokumentet

Slutligen kan du spara dokumentet med hjälp av Spara-metoden för klassen Document. Ange den fullständiga sökvägen till filen och önskat filnamn. Till exempel :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Se till att ersätta "dataDir" med katalogsökvägen till dina dokument.

## Exempel på källkod för DocSaveOptions-sparalternativ med "Spara inte Picture Bullet"-funktionalitet med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet med bildpunkter
Document doc = new Document(dataDir + "Image bullet points.docx");

// Konfigurera sparalternativ med funktionen "Spara inte Picture Bullet".
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Spara dokumentet med de angivna alternativen
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Slutsats

den här guiden behandlade vi hur du inaktiverar lagring av bildpunkter i ett dokument med Aspose.Words-biblioteket för .NET. Genom att följa de medföljande stegen och använda den medföljande C#-källkoden kan du enkelt tillämpa den här funktionen i din C#-applikation. Att inaktivera lagring av bildpunkter kan vara användbart i vissa situationer för att bevara dokumentstruktur och formatering utan att spara bildpunkter.