---
title: Mätenhet
linktitle: Mätenhet
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du anger måttenheten när du konverterar ett Word-dokument till ODT med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-odtsaveoptions/measure-unit/
---

När du konverterar ett Word-dokument till OpenDocument Text-format (ODT) i en C#-applikation, kanske du vill ange måttenheten som används för mätbar formatering och innehållsegenskaper. Med Aspose.Words-biblioteket för .NET kan du enkelt specificera denna funktionalitet med hjälp av OdtSaveOptions-sparalternativen. I den här steg-för-steg-guiden går vi igenom hur du använder Aspose.Words för .NET C#-källkod för att konvertera ett Word-dokument till ODT genom att ange måttenheten med OdtSaveOptions.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett kraftfullt bibliotek för att skapa, redigera, konvertera och skydda Word-dokument på olika plattformar inklusive .NET. Den erbjuder många funktioner för att manipulera dokument, som att infoga text, ändra formatering, lägga till avsnitt och mycket mer.

## Laddar Word-dokumentet

Det första steget är att ladda Word-dokumentet du vill konvertera till ODT. Använd klassen Document för att ladda dokumentet från källfilen. Här är ett exempel :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

I det här exemplet laddar vi dokumentet "Document.docx" som finns i dokumentkatalogen.

## Konfigurera alternativ för säkerhetskopiering

Nästa steg är att konfigurera alternativen för backup för konvertering till ODT. Använd klassen OdtSaveOptions och ställ in egenskapen MeasureUnit till önskat värde. Om du till exempel vill använda tum som måttenhet, ställ in MeasureUnit till OdtSaveMeasureUnit.Inches. Så här gör du:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Vi skapar ett nytt OdtSaveOptions-objekt och sätter egenskapen MeasureUnit till önskat värde, i vårt fall OdtSaveMeasureUnit.Inches för att använda tum som måttenhet.

## Konvertera dokument till ODT

Nu när vi har konfigurerat sparalternativen kan vi fortsätta att konvertera dokumentet till ODT. Använd metoden Spara för klassen Document för att spara det konverterade dokumentet i ODT-format genom att ange sparalternativ. Här är ett exempel :

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

I det här exemplet sparar vi det konverterade dokumentet som "WorkingWithOdtSaveOptions.MeasureUnit.odt" med de angivna sparalternativen.

### Exempel på källkod för OdtSaveOptions med funktionalitet "Mätenhet" med Aspose.Words för .NET



```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Ladda Word-dokumentet
Document doc = new Document(dataDir + "Document.docx");

// Konfiguration av reservalternativ med funktionen "Mätenhet".
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Konvertera dokumentet till ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Slutsats

den här guiden har vi förklarat hur man konverterar ett Word-dokument till ODT genom att ange måttenheten med hjälp av OdtSaveOptions-sparalternativen med Aspose.Words-biblioteket för .NET. Genom att följa de medföljande stegen och använda den medföljande C#-källkoden kan du enkelt tillämpa den här funktionen i din C#-applikation. Genom att specificera måttenheten vid konvertering till ODT kan du styra formateringen och dimensionerna för det resulterande dokumentet enligt dina specifika behov.