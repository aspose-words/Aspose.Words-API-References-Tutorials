---
title: Använd mellanslagstecken per nivå för listindrag
linktitle: Använd mellanslagstecken per nivå för listindrag
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att använda ett mellanslagstecken per nivå för listindrag i Aspose.Words för .NET. Skapa välstrukturerade Word-dokument med lätthet.
type: docs
weight: 10
url: /sv/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words för .NET är ett kraftfullt bibliotek för att skapa, redigera och manipulera Word-dokument i en C#-applikation. Bland funktionerna som erbjuds av Aspose.Words är möjligheten att använda ett blanksteg per nivå för indragning av listor. I den här guiden kommer vi att visa dig hur du använder C#-källkoden för Aspose.Words för .NET för att implementera denna funktionalitet.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett populärt bibliotek som gör arbetet med Word-dokument enkelt och effektivt. Den erbjuder ett brett utbud av funktioner för att skapa, ändra och manipulera Word-dokument, inklusive hantering av listor och indrag.

## Skapa dokumentet och lägga till innehåll

Det första steget är att skapa ett nytt dokument och lägga till innehåll till det. Använd klassen Document för att skapa en ny dokumentinstans. Använd sedan klassen DocumentBuilder för att lägga till text och skapa en lista med flera nivåer av indrag. Här är ett exempel :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa en lista med tre nivåer av indrag
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

I det här exemplet skapar vi ett nytt dokument och använder DocumentBuilder för att lägga till text och skapa en lista med tre nivåer av indrag. Vi har lagt till tre objekt till listan, med varje objekt indraget en extra nivå.

## Använder ett blanksteg per nivå för listindrag

När innehållet har lagts till kan vi nu konfigurera indragningen av listorna med ett blanksteg per nivå. För detta använder vi klassen TxtSaveOptions och vi ställer in egenskapen ListIndentation.Count till antalet indragsnivåer och egenskapen ListIndentation.Character till det blanksteg som ska användas. Här är hur:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

I det här exemplet skapar vi en instans av TxtSaveOptions och ställer in egenskapen ListIndentation.Count till 3 för att indikera att det finns tre nivåer av indrag i listan. Vi ställer också in egenskapen ListIndentation.Character till det blanksteg (' ') som vi vill använda för indrag.

### Exempel på källkod för funktionen "Använd ett blanksteg per nivå för listindrag" med Aspose.Words för .NET

Här är den kompletta källkoden för funktionen "Använd ett blanksteg per nivå för listindrag" med Aspose.Words för .NET:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Sökväg till din dokumentkatalog
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Skapa dokumentet och lägg till innehåll
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Skapa en lista med tre nivåer av indrag
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Använd ett blanksteg per nivå för listindrag
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // Spara dokumentet med de angivna alternativen
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## Slutsats

den här guiden förklarade vi hur man använder Aspose.Words för .NET för att tillämpa funktionen "Använd ett blanksteg per nivå för listindrag". Genom att följa de angivna stegen och använda den medföljande C#-källkoden kan du enkelt konfigurera indragningen av listor i dina Word-dokument med ett blanksteg per nivå. Aspose.Words erbjuder en enorm flexibilitet och kraft för att arbeta med textformatering och listhantering, vilket gör att du kan skapa välstrukturerade dokument i din C#-applikation.