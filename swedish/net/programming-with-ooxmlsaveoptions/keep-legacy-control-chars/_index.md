---
title: Behåll äldre kontrolltecken
linktitle: Behåll äldre kontrolltecken
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du bevarar äldre kontrolltecken när du sparar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

I den här handledningen kommer vi att utforska den medföljande C#-källkoden för att bevara äldre kontrolltecken när du sparar ett dokument med Aspose.Words för .NET. Med den här funktionen kan du bevara speciella kontrolltecken när du konverterar eller sparar ett dokument.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har ställt in din utvecklingsmiljö med Aspose.Words för .NET. Se till att du har lagt till nödvändiga referenser och importerat lämpliga namnområden.

## Steg 2: Ladda dokumentet

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 I det här steget laddar vi dokumentet med hjälp av`Document` metod och skickar sökvägen till filen som innehåller de ärvda kontrolltecknen.

## Steg 3: Konfigurera OOXML-säkerhetskopieringsalternativ

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 det här steget konfigurerar vi OOXML-sparalternativ genom att skapa ett nytt`OoxmlSaveOptions`objekt. Vi anger önskat sparaformat (här,`FlatOpc` ) och aktivera`KeepLegacyControlChars` möjlighet att behålla äldre kontrolltecken.

## Steg 4: Spara dokumentet med äldre kontrolltecken

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 I detta sista steg sparar vi dokumentet med hjälp av`Save` metod och skickar sökvägen till utdatafilen med`.docx` tillägg, tillsammans med de angivna sparalternativen.

Nu kan du köra källkod för att bevara äldre kontrolltecken när du sparar ett dokument. Den resulterande filen kommer att sparas i den angivna katalogen med namnet "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Exempel på källkod för Keep Legacy Control Chars med Aspose.Words för .NET 
```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Slutsats

I den här handledningen utforskade vi funktionaliteten för att bevara äldre kontrolltecken när du sparar ett dokument med Aspose.Words för .NET. Vi har lärt oss hur man bevarar de specialtecken som kan vara viktiga för korrekt formatering eller visning av dokument.

 Att bevara äldre kontrolltecken är särskilt användbart när du arbetar med dokument som använder äldre eller specifika funktioner, som speciella kontrolltecken. Genom att aktivera`KeepLegacyControlChars`när du sparar dokumentet ser du till att dessa tecken bevaras.

Aspose.Words för .NET erbjuder en rad flexibla och kraftfulla säkerhetskopieringsalternativ för att möta dina dokumenthanteringsbehov. Genom att använda lämpliga alternativ kan du anpassa säkerhetskopieringsprocessen för att bevara de specifika egenskaperna hos dina dokument.

Inkludera gärna denna funktion i dina Aspose.Words för .NET-projekt för att säkerställa integriteten och bevarandet av äldre kontrolltecken i dina dokument.