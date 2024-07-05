---
title: Ändra Toc-stil i Word-dokument
linktitle: Ändra Toc-stil i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du enkelt ändrar stilen på en innehållsförteckningsnivå i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-of-content/change-style-of-toc-level/
---
Aspose.Words för .NET är ett kraftfullt bibliotek för att skapa, redigera och manipulera Word-dokument i en C#-applikation. Bland funktionerna som erbjuds av Aspose.Words är möjligheten att ändra stilen på en viss nivå i ett dokuments innehållsförteckning. I den här guiden kommer vi att visa dig hur du använder C#-källkoden för Aspose.Words för .NET för att ändra stilen på en nivå i innehållsförteckningen i ett Word-dokument.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett populärt bibliotek som gör ordbehandling med Word-dokument enkelt och effektivt. Den erbjuder ett brett utbud av funktioner för att skapa, redigera och manipulera Word-dokument, inklusive att ändra stilen på innehållsförteckningen.

## Skapa ett nytt dokument

Det första steget är att skapa ett nytt Word-dokument där du vill ändra stilen för innehållsförteckningen. Använd klassen Document för att skapa ett nytt dokument. Här är ett exempel :

```csharp
Document doc = new Document();
```

I det här exemplet skapar vi ett nytt tomt dokument.

## Ändra stilen på en innehållsförteckningsnivå

När dokumentet har skapats kan du komma åt dokumentstilar och ändra stilen som används för en specifik nivå i innehållsförteckningen. I det här exemplet kommer vi att ändra stilen som används för den första nivån i innehållsförteckningen. Här är hur:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

I det här exemplet använder vi egenskapen Styles för klassen Document för att komma åt dokumentstilar. Därefter använder vi stilidentifieraren StyleIdentifier.Toc1 för att komma åt stilen som används för den första nivån i innehållsförteckningen. Slutligen ändrar vi egenskapen Font.Bold för stilen för att göra den fet.

## Spara ändrat dokument

När du har gjort de nödvändiga ändringarna av stilen på innehållsförteckningen kan du spara det ändrade dokumentet med hjälp av Spara-metoden för klassen Dokument. Här är ett exempel :

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

I det här exemplet sparar vi det ändrade dokumentet som "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx".

## Exempel på källkod för funktionen "Ändra stilen på en innehållsförteckningsnivå" med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa ett nytt dokument
Document doc = new Document();

// Ändring av stilen på den första nivån i innehållsförteckningen
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;

// Spara det ändrade dokumentet
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

## Slutsats

I den här guiden förklarade vi hur man använder Aspose.Words för .NET för att ändra stilen på en nivå i innehållsförteckningen i ett Word-dokument med hjälp av den medföljande C#-källkoden. Genom att följa de angivna stegen kan du enkelt anpassa stilen på innehållsförteckningen i dina Word-dokument i ditt C#-program. Aspose.Words erbjuder enorm flexibilitet och kraft att arbeta med stilarna och formateringen av dina dokument, vilket gör att du kan skapa attraktiva och professionella Word-dokument.

### Vanliga frågor för att ändra toc-stil i word-dokument

#### F: Vad är syftet med "Change Toc Style In Word Document"-funktionen i Aspose.Words för .NET?

S: Funktionen "Ändra innehållsformat i Word-dokument" i Aspose.Words för .NET låter dig ändra stilen för en specifik nivå i innehållsförteckningen i ett Word-dokument. Det gör att du kan anpassa utseendet och formateringen av innehållsförteckningen, som att ändra teckensnittsstil, storlek, färg eller andra visuella aspekter av en specifik nivå.

#### F: Vad är Aspose.Words för .NET?

S: Aspose.Words för .NET är ett kraftfullt bibliotek designat för ordbehandling med Word-dokument i .NET-applikationer. Den tillhandahåller omfattande funktioner för att skapa, redigera, manipulera och konvertera Word-dokument programmatiskt med C# eller andra .NET-språk.

#### F: Hur skapar jag ett nytt Word-dokument med Aspose.Words för .NET?

 S: För att skapa ett nytt Word-dokument med Aspose.Words för .NET, kan du använda`Document` klass och dess konstruktör. Genom att initiera en ny instans av`Document` klass kan du skapa ett tomt dokument. Här är ett exempel:

```csharp
Document doc = new Document();
```

Detta kodavsnitt skapar ett nytt, tomt Word-dokument.

#### F: Hur kan jag ändra stilen för en specifik nivå i innehållsförteckningen med Aspose.Words för .NET?

 S: När du har laddat ett dokument kan du ändra stilen för en specifik nivå i innehållsförteckningen genom att komma åt dokumentets stilar och göra nödvändiga ändringar. I Aspose.Words för .NET kan du använda`Styles` egendom av`Document` klass för att komma åt dokumentformaten och ändra sedan den önskade stilen med dess egenskaper. Till exempel, för att ändra stilen på den första nivån i innehållsförteckningen till fetstil, kan du använda följande kod:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

 I den här koden,`doc.Styles[StyleIdentifier.Toc1]` åtkomst till stilen för den första nivån i innehållsförteckningen, och`Font.Bold = true` anger den fetstilta stilen för den stilen.

#### F: Kan jag ändra stilen på flera nivåer i innehållsförteckningen med Aspose.Words för .NET?

 S: Ja, du kan ändra stilen på flera nivåer i innehållsförteckningen med Aspose.Words för .NET. För att ändra stilen för en specifik nivå kan du komma åt motsvarande stil med hjälp av`Styles`egendom och gör de önskade ändringarna för varje nivå individuellt.

#### F: Hur sparar jag det ändrade dokumentet efter att ha ändrat stilen på innehållsförteckningen med Aspose.Words för .NET?

 S: När du har gjort de nödvändiga ändringarna av stilen på innehållsförteckningen kan du spara det ändrade dokumentet med hjälp av`Save` metod för`Document` klass. Ange önskad filsökväg och namn för utdatadokumentet som en parameter till`Save` metod. Här är ett exempel:

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

Den här koden sparar det ändrade dokumentet som "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx".

#### F: Kan jag tillämpa andra formateringsändringar på innehållsförteckningen med Aspose.Words för .NET?

S: Ja, förutom att ändra stilen kan du tillämpa olika formateringsändringar på innehållsförteckningen med Aspose.Words för .NET. Du kan till exempel ändra teckenstorlek, färg, justering eller lägga till ytterligare formateringsegenskaper för att förbättra utseendet på innehållsförteckningen.

#### F: Hur kan jag specificera en anpassad stil för en specifik nivå i innehållsförteckningen med Aspose.Words för .NET?

 S: För att ange en anpassad stil för en specifik nivå i innehållsförteckningen med Aspose.Words för .NET, kan du skapa en ny`Style` objekt, konfigurera dess egenskaper enligt din önskade stil och tilldela det till motsvarande nivå i innehållsförteckningen med hjälp av`Styles` egendom av`Document` klass. Detta låter dig definiera en anpassad stil för en specifik nivå baserat på dina krav.

#### F: Kan jag ändra stilen på innehållsförteckningen i ett befintligt Word-dokument med Aspose.Words för .NET?

 S: Ja, du kan ändra stilen på innehållsförteckningen i ett befintligt Word-dokument med Aspose.Words för .NET. Ladda helt enkelt dokumentet med hjälp av`Document` klass, ändra stilegenskaperna med hjälp av`Styles` egenskap och spara dokumentet för att tillämpa ändringarna.

#### F: Har Aspose.Words för .NET stöd för att ändra andra stilar och formatering i Word-dokument?

S: Ja, Aspose.Words för .NET ger omfattande stöd för att ändra olika stilar och formatering i Word-dokument. Det låter dig ändra stilar för olika element som stycken, rubriker, tabeller, listor och mer. Du kan ändra teckensnitt, färger, justering, indrag, avstånd och andra formateringsaspekter enligt dina krav.