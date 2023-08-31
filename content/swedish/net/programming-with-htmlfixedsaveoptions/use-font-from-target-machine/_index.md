---
title: Använd teckensnitt från målmaskin
linktitle: Använd teckensnitt från målmaskin
second_title: Aspose.Words Document Processing API
description: Lär dig hur du konverterar ett Word-dokument till fast HTML med hjälp av målmaskinens teckensnitt med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

När du konverterar ett Word-dokument till fast HTML i en C#-applikation, kanske du vill använda målmaskinens teckensnitt för att säkerställa att den renderade HTML-koden behåller dokumentets ursprungliga utseende och stil. Med Aspose.Words-biblioteket för .NET kan du enkelt specificera denna funktionalitet med hjälp av HtmlFixedSaveOptions-sparalternativen. I den här steg-för-steg-guiden går vi igenom hur du använder C#-källkoden för Aspose.Words för .NET för att konvertera ett Word-dokument till fast HTML med hjälp av målmaskinens teckensnitt med hjälp av HtmlFixedSaveOptions.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett kraftfullt bibliotek för att skapa, redigera, konvertera och skydda Word-dokument på olika plattformar inklusive .NET. Den erbjuder många funktioner för att manipulera dokument, som att infoga text, ändra formatering, lägga till avsnitt och mycket mer.

## Laddar Word-dokumentet

Det första steget är att ladda Word-dokumentet du vill konvertera till fast HTML. Använd klassen Document för att ladda dokumentet från källfilen. Här är ett exempel :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

I det här exemplet laddar vi dokumentet "Punktpunkter med alternativt teckensnitt.docx" som finns i dokumentkatalogen.

## Konfigurera alternativ för säkerhetskopiering

Nästa steg är att konfigurera sparalternativen för konvertering till fast HTML. Använd klassen HtmlFixedSaveOptions och ställ in egenskapen UseTargetMachineFonts på true för att tala om för Aspose.Words att använda teckensnitt från måldatorn. Så här gör du:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Vi skapar ett nytt HtmlFixedSaveOptions-objekt och ställer in UseTargetMachineFonts-egenskapen till true för att använda målmaskinens teckensnitt vid konvertering.

## Fast HTML-dokumentkonvertering

Nu när vi har konfigurerat sparalternativen kan vi fortsätta att konvertera dokumentet till fast HTML. Använd metoden Spara för klassen Document för att spara det konverterade dokumentet i fast HTML-format genom att ange sparalternativ. Här är ett exempel :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

I det här exemplet sparar vi det konverterade dokumentet som "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" med de angivna sparalternativen.

### Exempel på källkod för HtmlFixedSaveOptions med funktionen "Använd teckensnitt från målmaskin" med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda Word-dokumentet
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//Konfigurera alternativ för säkerhetskopiering med funktionen "Använd teckensnitt från måldator".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Konvertera dokument till fast HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Slutsats

I den här guiden har vi förklarat hur man konverterar ett Word-dokument till fast HTML med hjälp av målmaskinens teckensnitt med Aspose.Words-biblioteket för .NET. Genom att följa de medföljande stegen och använda den medföljande C#-källkoden kan du enkelt tillämpa den här funktionen i din C#-applikation. Konverteringen till fast HTML med målmaskinens teckensnitt garanterar trogen och konsekvent rendering av dokumentet i HTML-format.
