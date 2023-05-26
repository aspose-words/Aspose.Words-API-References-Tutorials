---
title: Ladda Chm
linktitle: Ladda Chm
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du laddar CHM-filer med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-loadoptions/load-chm/
---

När du arbetar med HTML-hjälpfiler (CHM) i en C#-applikation är det viktigt att kunna ladda dem korrekt. Med Aspose.Words-biblioteket för .NET kan du enkelt ladda CHM-filer med lämpliga laddningsalternativ. I denna steg-för-steg-guide kommer vi att visa dig hur du använder Aspose.Words för .NET C#-källkod för att ladda en CHM-fil med hjälp av LoadOptions laddningsalternativ.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett kraftfullt bibliotek för att skapa, redigera, konvertera och skydda Word-dokument på olika plattformar inklusive .NET. Den erbjuder många funktioner för att manipulera dokument, som att infoga text, ändra formatering, lägga till avsnitt och mycket mer.

## Konfigurera laddningsalternativ

Det första steget är att konfigurera laddningsalternativen för vår CHM-fil. Använd klassen LoadOptions för att ange laddningsparametrar. I vårt fall måste vi ställa in Encoding-egenskapen till lämplig kodning för CHM-filer, vanligtvis "windows-1251". Så här gör du:

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };
```

Vi skapar ett nytt LoadOptions-objekt och ställer in Encoding-egenskapen till "windows-1251"-kodning för CHM-filer.

## Laddar CHM-fil

Nu när vi har konfigurerat laddningsalternativen kan vi ladda CHM-filen med klassen Document och specificera laddningsalternativen. Här är ett exempel :

```csharp
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

I det här exemplet laddar vi CHM-filen "HTML help.chm" som finns i dokumentkatalogen med de angivna laddningsalternativen.

### Exempel på källkod för LoadOptions med "Load Chm"-funktionalitet med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfiguration av laddningsalternativen med "Load Chm"-funktionen
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };

// Ladda CHM-filen med de angivna alternativen
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

## Slutsats

den här guiden förklarade vi hur man laddar en CHM-fil med Aspose.Words-biblioteket för .NET. Genom att följa de medföljande stegen och använda den medföljande C#-källkoden kan du enkelt tillämpa den här funktionen i din C#-applikation. Att ladda CHM-filer korrekt är viktigt för att kunna manipulera och konvertera dem effektivt med Aspose.Words.