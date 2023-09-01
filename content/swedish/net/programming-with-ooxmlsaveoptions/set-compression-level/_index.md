---
title: Ställ in komprimeringsnivå
linktitle: Ställ in komprimeringsnivå
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ställer in komprimeringsnivån när du sparar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
den här handledningen kommer vi att utforska den medföljande C#-källkoden för att ställa in komprimeringsnivån när du sparar ett dokument med Aspose.Words för .NET. Denna funktion låter dig styra komprimeringsnivån för det genererade dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har ställt in din utvecklingsmiljö med Aspose.Words för .NET. Se till att du har lagt till nödvändiga referenser och importerat lämpliga namnområden.

## Steg 2: Ladda dokumentet

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 I det här steget laddar vi dokumentet med hjälp av`Document` metod och skickar sökvägen till DOCX-filen som ska laddas.

## Steg 3: Konfigurera OOXML-säkerhetskopieringsalternativ

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 I det här steget konfigurerar vi OOXML-sparalternativ med hjälp av`OoxmlSaveOptions` klass. Vi ställer in kompressionsnivån till`SuperFast` för att få snabbare komprimering.

## Steg 4: Spara dokumentet med den angivna komprimeringsnivån

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 I detta sista steg sparar vi dokumentet med hjälp av`Save` metod och skickar sökvägen till utdatafilen med`.docx` tillägg, tillsammans med de angivna sparalternativen.

Nu kan du köra källkoden för att ställa in komprimeringsnivån när du sparar ett dokument. Den resulterande filen kommer att sparas i den angivna katalogen med namnet "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### Exempel på källkod för Set Compression Level med Aspose.Words för .NET 

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Slutsats

I den här handledningen utforskade vi funktionaliteten för att ställa in komprimeringsnivån när du sparar ett dokument med Aspose.Words för .NET. Genom att ange lämplig komprimeringsnivå kan du optimera dokumentstorlek och genereringshastighet.

 De`OoxmlSaveOptions`klass ger flexibilitet för att kontrollera komprimeringsnivån genom att ställa in`CompressionLevel` egendom till lämpligt värde, som t.ex`SuperFast`. Detta gör att du kan hitta rätt balans mellan filstorlek och säkerhetskopieringshastighet baserat på dina specifika behov.

Att använda komprimering kan vara fördelaktigt när du behöver minska storleken på genererade filer, särskilt för stora dokument. Detta kan göra det lättare att lagra, dela och överföra dokument.

Aspose.Words för .NET erbjuder en rad kraftfulla alternativ och funktioner för dokumenthantering. Genom att använda lämpliga säkerhetskopieringsalternativ kan du anpassa dokumentgenereringsprocessen och optimera din applikations prestanda.

Utforska gärna fler funktioner i Aspose.Words för .NET för att förbättra ditt arbetsflöde för dokumentgenerering.
