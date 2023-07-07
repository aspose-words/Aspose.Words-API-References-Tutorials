---
title: Ersätt hyperlänkar
linktitle: Ersätt hyperlänkar
second_title: Aspose.Words för .NET API Referens
description: Ersätt hyperlänkar i Word-dokument med Aspose.Words för .NET. Steg-för-steg-instruktioner för att ersätta hyperlänkar.
type: docs
weight: 10
url: /sv/net/working-with-fields/replace-hyperlinks/
---

Här är en steg-för-steg-guide för att förklara följande C#-källkod för att ersätta hyperlänkar med Aspose.Words för .NET-funktionalitet. Se till att du har inkluderat Aspose.Words-biblioteket i ditt projekt innan du använder den här koden.

## Steg 1: Ange sökväg till dokumentkatalogen

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Var noga med att ange rätt sökväg till din dokumentkatalog som innehåller`Hyperlinks.docx` fil.

## Steg 2: Ladda dokumentet som innehåller hyperlänkarna

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Här skapar vi en instans av`Document` klass från den angivna filen.

## Steg 3: Bläddra i fälten för att hitta hyperlänkar

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Vissa hyperlänkar kan vara lokala (länkar till bokmärken inuti dokumentet), vi ignorerar dem.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Denna loop går igenom alla fält i dokumentet och letar efter typfält`FieldType.FieldHyperlink` . När ett fält av den här typen har hittats kontrollerar vi om det är en lokal länk genom att markera`SubAddress` fast egendom. Om inte, ersätter vi länkadressen med`"http://www.aspose.com"` och resultatet med`"Aspose - The .NET & Java Component Editor"`.

## Steg 4: Spara det ändrade dokumentet

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Slutligen sparar vi det modifierade dokumentet med de ersatta hyperlänkarna till en specificerad fil.

### Exempel på källkod för att ersätta hyperlänkar med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Vissa hyperlänkar kan vara lokala (länkar till bokmärken inuti dokumentet), vi ignorerar dem.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Detta är exempel på källkod för att ersätta hyperlänkar i ett dokument med Aspose.Words för .NET.

### FAQ's

#### F: Hur kan jag ersätta hyperlänkar i ett Word-dokument med Aspose.Words för .NET?

 S: För att ersätta hyperlänkar i ett Word-dokument med Aspose.Words för .NET kan du använda`Document.Range.Replace`metod som anger texten som ska sökas efter och ersättningstexten. Se till att använda lämpliga alternativ för att ställa in sök- och ersättningsparametrar.

#### F: Är det möjligt att endast ersätta vissa hyperlänkar i ett Word-dokument med Aspose.Words för .NET?

S: Ja, det är möjligt att endast ersätta vissa hyperlänkar i ett Word-dokument med Aspose.Words för .NET. Du kan filtrera hyperlänkarna som ska ersättas med hjälp av specifika kriterier, såsom länkadress, länktext eller någon annan relevant egenskap. Då kan du tillämpa ersättningen endast på de matchande hyperlänkarna.

#### F: Hur kan jag ignorera hyperlänkar i sidhuvuden, sidfötter eller fotnoter när jag ersätter med Aspose.Words för .NET?

S: För att ignorera hyperlänkar i sidhuvuden, sidfötter eller fotnoter när du ersätter med Aspose.Words för .NET, kan du använda de avancerade sökalternativen och ange lämpliga sökgränser. Du kan till exempel begränsa sökningen till större delar av dokumentet och utesluta sidhuvuden, sidfötter eller fotnoter.

#### F: Är det möjligt att ersätta hyperlänkar med interna länkar till andra delar av dokumentet?

 S: Ja, det är möjligt att ersätta hyperlänkar med interna länkar till andra delar av dokumentet med Aspose.Words för .NET. Du kan använda ankare eller text-ID för att skapa interna länkar och sedan ersätta dem med hjälp av`Document.Range.Replace` metod med lämpliga alternativ.

#### F: Behåller ersättning av hyperlänkar med Aspose.Words för .NET länkegenskaper, såsom färger eller stilar?

S: Ja, när du ersätter hyperlänkar med Aspose.Words för .NET, behålls länkegenskaper som färger eller stilar. Du kan ange samma formateringsegenskaper i ersättningstexten för att uppnå ett konsekvent resultat.