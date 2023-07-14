---
title: Komprimera inte små metafiler
linktitle: Komprimera inte små metafiler
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder Aspose.Words för .NET för att aktivera funktionen Komprimera inte små metafiler när du sparar dokument.
type: docs
weight: 10
url: /sv/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

Att komprimera metadata i ett dokument är en vanlig funktion vid ordbehandling med filer i en C#-applikation. Det kan dock vara nödvändigt att inte komprimera metadata för små filer för att bevara deras kvalitet. I den här steg-för-steg-guiden visar vi dig hur du använder C#-källkoden för Aspose.Words för .NET för att aktivera funktionen "Komprimera inte små metafiler" i alternativen för att spara dokument.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett kraftfullt bibliotek för att skapa, redigera, konvertera och skydda Word-dokument på olika plattformar inklusive .NET. Den erbjuder många funktioner för att manipulera dokument, som att infoga text, ändra formatering, lägga till avsnitt och mycket mer.

## Steg 1: Ställ in dokumentkatalog

Det första steget är att definiera katalogen där du vill spara dokumentet. Du måste ange den fullständiga katalogsökvägen. Till exempel :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: Infoga avsnitt och text

Sedan kan du infoga avsnitt och text i ditt dokument. Använd klassen DocumentBuilder från Aspose.Words för att bygga innehållet i ditt dokument. Här är ett enkelt exempel:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

I det här exemplet skapar vi ett nytt tomt dokument och använder sedan DocumentBuilder för att lägga till en textrad.

## Steg 3: Inställningsalternativ

'registrering

Låt oss nu konfigurera sparalternativen för vårt dokument. Använd klassen DocSaveOptions för att ange sparinställningar. Till exempel :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

I det här exemplet skapar vi ett nytt DocSaveOptions-objekt för att ställa in sparalternativ.

## Steg 4: Aktivera funktionen "Komprimera inte små metafiler".

 För att aktivera funktionen "Komprimera inte små metafiler" måste du ställa in`Compliance` egenskapen för DocSaveOptions-objektet till värdet`PdfCompliance.PdfA1a`. Här är hur:

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

Denna konfiguration säkerställer att metadata för små filer inte komprimeras när dokumentet sparas.

## Steg 5: Spara dokumentet

Slutligen kan du spara dokumentet med hjälp av`Save` metoden för klassen Document. Ange den fullständiga sökvägen till filen och önskat filnamn. Till exempel :

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

Se till att ersätta "dataDir" med sökvägen till din dokumentkatalog.

### Exempel på källkod för DocSaveOptions med funktionen Komprimera inte små metafiler med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Infoga två avsnitt med lite text.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Konfigurera sparalternativ med funktionen "Komprimera inte små metafiler".
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

// Spara dokumentet med de angivna alternativen
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## Slutsats

I den här guiden förklarade vi hur du använder Aspose.Words-biblioteket för .NET för att aktivera funktionen "Komprimera inte små metafiler" när du sparar ett dokument. Genom att följa de medföljande stegen och använda den medföljande C#-källkoden kan du enkelt tillämpa den här funktionen i din C#-applikation. Att bevara okomprimerad metadata för små filer kan vara viktigt för att upprätthålla dokumentkvalitet och integritet.