---
title: Ställ in Ms Word-version
linktitle: Ställ in Ms Word-version
second_title: Aspose.Words Document Processing API
description: Lär dig hur du laddar ett dokument med en specificerad version av MS Word med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-loadoptions/set-ms-word-version/
---
Vid ordbehandling med Word-dokument i en C#-applikation kan det vara nödvändigt att ange vilken version av Microsoft Word som ska användas när dokumentet laddas. Med Aspose.Words-biblioteket för .NET kan du enkelt ställa in vilken version av MS Word som ska användas med LoadOptions. I denna steg-för-steg-guide kommer vi att gå igenom hur du använder Aspose.Words för .NET C#-källkod för att ladda ett dokument med en specificerad version av MS Word med hjälp av LoadOptions laddningsalternativ.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett kraftfullt bibliotek för att skapa, redigera, konvertera och skydda Word-dokument på olika plattformar inklusive .NET. Den erbjuder många funktioner för att manipulera dokument, som att infoga text, ändra formatering, lägga till avsnitt och mycket mer.

## Konfigurera laddningsalternativ

Det första steget är att konfigurera laddningsalternativen för vårt dokument. Använd klassen LoadOptions för att ange laddningsparametrar. I vårt fall måste vi ställa in MswVersion-egenskapen till den önskade versionen av MS Word. Till exempel använder vi Microsoft Word 2010 version. Så här gör du:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Vi skapar ett nytt LoadOptions-objekt och ställer in MswVersion-egenskapen till MsWordVersion.Word2010 för att ange versionen av MS Word 2010.

## Dokument laddas med specificerad version av MS Word

Nu när vi har konfigurerat laddningsalternativen kan vi ladda dokumentet med klassen Document och ange laddningsalternativen. Här är ett exempel :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

det här exemplet laddar vi dokumentet "Document.docx" som finns i dokumentkatalogen med de angivna laddningsalternativen.

### Exempel på källkod för LoadOptions med "Set MS Word Version"-funktionalitet med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfigurera laddningsalternativ med funktionen "Set MS Word Version".
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Ladda dokumentet med den angivna versionen av MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Spara dokumentet
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Slutsats

I den här guiden har vi förklarat hur man laddar upp ett dokument som anger en specifik version av MS Word med hjälp av Aspose.Words-biblioteket för .NET. Genom att följa de medföljande stegen och använda koden C#-källa som tillhandahålls kan du enkelt tillämpa denna funktionalitet i din C#-applikation. Genom att ladda ett dokument med en specificerad version av MS Word kan du säkerställa korrekt kompatibilitet och bearbetning av dokumentet i din applikation.


### FAQ's

#### F: Varför skulle jag behöva ange versionen av MS Word när jag laddar ett dokument i en C#-applikation?

Att specificera versionen av MS Word säkerställer att dokumentet laddas och bearbetas korrekt, särskilt när det handlar om specifik formatering eller funktioner som kan variera mellan olika versioner.

#### F: Vilka versioner av MS Word stöder Aspose.Words?

S: Aspose.Words för .NET stöder olika versioner av MS Word, inklusive Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 och mer.

#### F: Kan jag ladda ett dokument med en annan version av MS Word än den som är installerad på mitt system?

S: Ja, Aspose.Words låter dig ange en annan version av MS Word när du laddar dokumentet, vilket säkerställer kompatibilitet även om målsystemet har en annan MS Word-version.

#### F: Hur gynnar min C#-applikation att ställa in MS Word-versionen?

S: Att ställa in MS Word-versionen säkerställer att dokumentet bearbetas i enlighet med den avsedda formateringen och funktionerna i den specifika versionen, vilket ger konsekvent utdata.

#### F: Är Aspose.Words begränsad till att endast hantera DOCX-dokument?

S: Nej, Aspose.Words stöder olika dokumentformat, inklusive DOC, RTF, HTML, PDF och mer, vilket gör det till ett mångsidigt verktyg för att hantera olika typer av dokument.