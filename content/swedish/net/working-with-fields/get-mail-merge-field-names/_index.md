---
title: Hämta fältnamn för sammankoppling av brev
linktitle: Hämta fältnamn för sammankoppling av brev
second_title: Aspose.Words Document Processing API
description: Lär dig hur du får kopplingsfältnamn i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/get-mail-merge-field-names/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Get Merge Field Names" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet

Det första steget är att ladda dokumentet där du vill hämta sammanslagningsfältnamnen.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Se till att ersätta "DIN DOKUMENTFIL" med namnet på din egen fil.

## Steg 3: Hämta sammanslagningsfältnamn

 Vi använder`GetFieldNames()` metod för att få en array som innehåller namnen på de sammanslagningsfält som finns i dokumentet.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 De`fieldNames` variabeln innehåller nu namnen på sammanslagningsfälten.

### Källkodsexempel för Get Merge-fältnamn med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Hämta sammanslagna fältnamn.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Visa antalet sammanslagningsfält.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 I det här exemplet laddade vi ett dokument, fick sammanslagningsfältsnamnen med hjälp av`GetFieldNames()` metod och visade antalet sammanslagningsfält som finns i dokumentet.

Detta avslutar vår guide om hur du använder funktionen "Get Merge Field Names" med Aspose.Words för .NET.

### Vanliga frågor

#### F1: Vad är e-postkoppling i Aspose.Words?

Mail merge i Aspose.Words är en process för att slå samman data från en extern källa (t.ex. Excel-kalkylblad eller databas) med en mall i Word-dokument för att skapa personliga dokument. Detta underlättar automatisk generering av brev, rapporter och andra liknande dokument.

#### F2: Hur får jag listan över kopplingsfält som är tillgängliga i ett Word-dokument?

För att få listan över kopplingsfält som är tillgängliga i ett Word-dokument kan du följa dessa steg:

1. Importera klasserna Document och MailMergeFieldNames från namnområdet Aspose.Words.
2. Skapa en dokumentinstans genom att ladda ditt Word-dokument.
3. Använd dokumentobjektets GetMailMergeFieldNames-metod för att få listan över tillgängliga kopplingsfält.

Här är en exempelkod för att illustrera processen:

```csharp
// Importera de nödvändiga namnrymden
using Aspose.Words;
using Aspose.Words.MailMerging;

// Ladda det befintliga dokumentet
Document document = new Document("FilePath");

// Hämta lista över kopplingsfält
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Bläddra genom tillgängliga kopplingsfält
foreach (string fieldName in fieldNames)
{
     // Gör något med fältnamnet
     Console.WriteLine(fieldName);
}
```
### FAQ's

#### F: Vad är e-postkoppling i Aspose.Words?

S: Mail merge i Aspose.Words är en process för att slå samman data från en extern källa (t.ex. Excel-kalkylblad eller databas) med en mall i Word-dokument för att skapa personliga dokument. Detta underlättar automatisk generering av brev, rapporter och andra liknande dokument.

#### F: Hur får jag en lista över kopplingsfält som är tillgängliga i ett Word-dokument?

S: För att få listan över kopplingsfält som är tillgängliga i ett Word-dokument kan du följa dessa steg:

1. Importera klasserna Document och MailMergeFieldNames från namnområdet Aspose.Words.
2. Skapa en dokumentinstans genom att ladda ditt Word-dokument.
3. Använd dokumentobjektets GetMailMergeFieldNames-metod för att få listan över tillgängliga kopplingsfält.

#### F: Kan jag få kopplingsfält från en extern datakälla som ett Excel-kalkylblad?

S: Ja, du kan hämta kopplingsfälten från en extern datakälla som ett Excel-kalkylblad. För detta kan du använda databindningsfunktionerna i Aspose.Words för att upprätta en anslutning till datakällan och få namnen på de tillgängliga fälten.

#### F: Är det möjligt att filtrera sammanslagningsfält baserat på vissa kriterier?

S: Ja, det är möjligt att filtrera sammanslagningsfält baserat på vissa kriterier. Du kan använda reguljära uttryck eller specifika villkor för att filtrera sammanslagningsfält och bara få de som uppfyller dina specifika kriterier.

#### F: Hur kan jag manipulera kopplingsfält i Aspose.Words?

S: För att manipulera kopplingsfält i Aspose.Words kan du använda metoderna och egenskaperna som tillhandahålls av objekten Document och MailMergeField. Du kan lägga till, ta bort eller uppdatera sammanslagningsfält, samt hämta och redigera värden som är associerade med fält.