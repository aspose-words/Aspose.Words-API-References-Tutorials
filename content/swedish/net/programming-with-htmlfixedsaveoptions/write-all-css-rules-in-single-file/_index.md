---
title: Skriv alla CSS-regler i en fil
linktitle: Skriv alla CSS-regler i en fil
second_title: Aspose.Words Document Processing API
description: Lär dig hur du konverterar ett Word-dokument till fast HTML genom att skriva alla CSS-regler i en enda fil med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

När du konverterar ett Word-dokument till fast HTML i en C#-applikation, kanske du vill konsolidera alla CSS-regler till en enda fil för bättre organisation och portabilitet. Med Aspose.Words-biblioteket för .NET kan du enkelt specificera denna funktionalitet med hjälp av HtmlFixedSaveOptions-sparalternativen. I den här steg-för-steg-guiden går vi igenom hur du använder Aspose.Words för .NET C#-källkod för att konvertera ett Word-dokument till fast HTML genom att skriva alla CSS-regler i en enda fil med hjälp av sparaalternativ HtmlFixedSaveOptions.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett kraftfullt bibliotek för att skapa, redigera, konvertera och skydda Word-dokument på olika plattformar inklusive .NET. Den erbjuder många funktioner för att manipulera dokument, som att infoga text, ändra formatering, lägga till avsnitt och mycket mer.

## Laddar Word-dokumentet

Det första steget är att ladda Word-dokumentet du vill konvertera till fast HTML. Använd klassen Document för att ladda dokumentet från källfilen. Här är ett exempel :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

I det här exemplet laddar vi dokumentet "Document.docx" som finns i dokumentkatalogen.

## Konfigurera alternativ för säkerhetskopiering

Nästa steg är att konfigurera sparalternativen för konvertering till fast HTML. Använd klassen HtmlFixedSaveOptions och ställ in egenskapen SaveFontFaceCssSeparately till false för att skriva alla CSS-regler i en enda fil. Så här gör du:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Vi skapar ett nytt HtmlFixedSaveOptions-objekt och ställer in egenskapen SaveFontFaceCssSeparately till false för att skriva alla CSS-regler i en enda fil.

## Fast HTML-dokumentkonvertering

Nu när vi har konfigurerat sparalternativen kan vi fortsätta att konvertera dokumentet till fast HTML. Använd metoden Spara för klassen Document för att spara det konverterade dokumentet i fast HTML-format genom att ange sparalternativ. Här är ett exempel :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

det här exemplet sparar vi det konverterade dokumentet som "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" med de angivna sparalternativen.

### Exempel på källkod för HtmlFixedSaveOptions med funktionen "Skriv alla CSS-regler i en fil" med Aspose.Words för .NET

```csharp
// Åtkomstsökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda Word-dokumentet
Document doc = new Document(dataDir + "Document.docx");

// Konfigurera alternativ för säkerhetskopiering med funktionen "Skriv alla CSS-regler i en fil".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Konvertera dokument till fast HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Slutsats

I den här guiden har vi tagit upp hur man konverterar ett Word-dokument till fast HTML genom att skriva alla CSS-regler i en enda fil med hjälp av HtmlFixedSaveOptions med Aspose.Words-biblioteket för .NET. Genom att följa de medföljande stegen och använda den medföljande C#-källkoden kan du enkelt tillämpa den här funktionen i din C#-applikation. Att skriva alla CSS-regler i en enda fil gör det lättare att organisera och hantera HTML-koden som genereras under dokumentkonverteringen.