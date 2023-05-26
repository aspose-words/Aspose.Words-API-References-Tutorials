---
title: Uppdatera egenskapen Senaste sparad tid
linktitle: Uppdatera egenskapen Senaste sparad tid
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du automatiskt uppdaterar egenskapen Last Saved Time när du sparar ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
den här handledningen kommer vi att utforska den medföljande C#-källkoden för att uppdatera den senaste spartid-egenskapen när du sparar ett dokument med Aspose.Words för .NET. Med den här funktionen kan du automatiskt uppdatera den senast sparade tidsegenskapen för det genererade dokumentet.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 I det här steget konfigurerar vi OOXML-sparalternativ med hjälp av`OoxmlSaveOptions` klass. Vi aktiverar automatisk uppdatering av den senaste spartidsegenskapen genom att ställa in`UpdateLastSavedTimeProperty` till`true`.

## Steg 4: Spara dokument med uppdaterad egenskap

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 I detta sista steg sparar vi dokumentet med hjälp av`Save` metod och skickar sökvägen till utdatafilen med`.docx` tillägg, tillsammans med de angivna sparalternativen.

Nu kan du köra källkoden för att automatiskt uppdatera egenskapen för senaste spartid när du sparar ett dokument. Den resulterande filen kommer att sparas i den angivna katalogen med namnet "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Exempel på källkod för Update Last Saved Time Property med Aspose.Words för .NET 

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Slutsats

den här handledningen utforskade vi funktionen att automatiskt uppdatera den senaste spartid-egenskapen när du sparar ett dokument med Aspose.Words för .NET. Genom att aktivera den här funktionen med OOXML-sparalternativ kan du säkerställa att den senaste spartid-egenskapen uppdateras automatiskt i det genererade dokumentet.

Att uppdatera egenskapen för senaste spartid kan vara användbart för att spåra ändringar och versioner av ett dokument. Den håller också reda på när dokumentet senast sparades, vilket kan vara användbart i olika scenarier.

Aspose.Words för .NET gör det enkelt att automatiskt uppdatera egenskapen Last Backup Time genom att tillhandahålla flexibla och kraftfulla säkerhetskopieringsalternativ. Du kan integrera den här funktionen i dina projekt för att säkerställa att genererade dokument har korrekt säkerhetskopieringsinformation.