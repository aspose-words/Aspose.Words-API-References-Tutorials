---
title: Spara bilder som Wmf
linktitle: Spara bilder som Wmf
second_title: Aspose.Words Document Processing API
description: Lär dig hur du sparar bilder som WMF när du konverterar till RTF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-rtfsaveoptions/saving-images-as-wmf/
---

I den här handledningen kommer vi att utforska C#-källkoden som tillhandahålls för funktionen "Spara bilder som WMF med RTF-sparalternativ" med Aspose.Words för .NET. Med den här funktionen kan du spara dokumentbilder i Windows Metafile-format (WMF) när du konverterar till RTF-format.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har ställt in din utvecklingsmiljö med Aspose.Words för .NET. Se till att du har lagt till nödvändiga referenser och importerat lämpliga namnområden.

## Steg 2: Ladda dokumentet

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 I det här steget laddar vi dokumentet med hjälp av`Document` metod och skickar sökvägen till DOCX-filen som ska laddas.

## Steg 3: Konfigurera alternativ för säkerhetskopiering

```csharp
RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };
```

 I det här steget konfigurerar vi alternativen för RTF-säkerhetskopiering. Vi skapar en ny`RtfSaveOptions` objekt och ställ in`SaveImagesAsWmf` egendom till`true`. Detta säger till Aspose.Words att spara dokumentbilderna som WMF vid konvertering till RTF.

## Steg 4: Spara dokumentet

```csharp
doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```

 I detta sista steg sparar vi det resulterande dokumentet i RTF-format med hjälp av`Save` metod och skicka sökvägen till utdatafilen, tillsammans med de angivna sparaalternativen.

Nu kan du köra källkod för att spara dokumentbilder i WMF-format samtidigt som du konverterar till RTF-format. Det resulterande dokumentet kommer att sparas i den angivna katalogen med namnet "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf".

### Exempel på källkod för funktionalitet för att spara WMF-bilder med RTF-sparalternativ med Aspose.Words för .NET".

```csharp

            
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");

RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };

doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
            
        
```
## Slutsats

I den här handledningen utforskade vi funktionaliteten för att spara bilder som WMF med RTF-sparalternativ i Aspose.Words för .NET. Vi lärde oss hur man sparar bilder från ett dokument i WMF-format när man konverterar till RTF-format.

Den här funktionen är användbar när du vill behålla kvaliteten och upplösningen på bilder i dina RTF-dokument. Genom att spara bilder i WMF-format kan du säkerställa att deras utseende och skärpa förblir intakta.

Aspose.Words för .NET erbjuder många avancerade funktioner för dokumenthantering och generering. Att spara bilder i WMF-format medan du konverterar till RTF-format är ett av de många kraftfulla verktyg det ger dig.

### Vanliga frågor

#### F: Vad är funktionen "Spara bilder som WMF med RTF-sparalternativ" med Aspose.Words för .NET?
S: Funktionen "Spara bilder som WMF med RTF-sparalternativ" med Aspose.Words för .NET tillåter att dokumentbilder sparas i Windows Metafile-format (WMF) vid konvertering till RTF. Detta ger möjligheten att behålla bildkvalitet och upplösning i RTF-dokument.

#### F: Hur kan jag använda den här funktionen med Aspose.Words för .NET?
S: För att använda den här funktionen med Aspose.Words för .NET kan du följa dessa steg:

Ställ in din utvecklingsmiljö genom att lägga till nödvändiga referenser och importera lämpliga namnområden.

 Ladda dokumentet med hjälp av`Document` metod och ange sökvägen till DOCX-filen som ska laddas.

 Konfigurera RTF-sparalternativ genom att skapa en`RtfSaveOptions` objekt och ställa in`SaveImagesAsWmf` egendom till`true`. Detta säger till Aspose.Words att spara dokumentbilderna som 
WMF vid konvertering till RTF.

 Spara det resulterande dokumentet i RTF-format med hjälp av`Save` metod och ange den fullständiga sökvägen till utdatafilen, tillsammans med de angivna sparalternativen.

#### F: Är det möjligt att välja ett annat bildformat för att spara med RTF-sparalternativ?
S: Nej, den här specifika funktionen sparar bilder i WMF-format vid konvertering till RTF. Andra bildformat stöds inte direkt av den här funktionen. Men Aspose.Words erbjuder andra funktioner för bildmanipulation och konvertering, vilket gör att du kan konvertera bilder till andra format före eller efter konvertering till RTF.

#### F: Ger RTF-lagringsalternativen med Aspose.Words för .NET andra funktioner?
S: Ja, Aspose.Words för .NET erbjuder många fler funktioner med RTF-sparalternativ. Du kan anpassa olika aspekter av RTF-konvertering, såsom teckensnittshantering, layout, bilder, tabeller, hyperlänkar, etc. Dessa alternativ ger dig exakt kontroll över slutresultatet av RTF-konverteringen.

#### F: Hur kan jag manipulera bilder i ett dokument med Aspose.Words för .NET?
S: Aspose.Words för .NET erbjuder ett komplett utbud av funktioner för att manipulera bilder i ett dokument. Du kan extrahera, infoga, ändra storlek, beskära, tillämpa filter och effekter, justera kvalitet, konvertera mellan olika bildformat och mycket mer. Se Aspose.Words-dokumentationen för mer information om bildmanipulation.