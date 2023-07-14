---
title: Tillåt endast formulärfält att skydda i Word-dokument
linktitle: Tillåt endast formulärfält att skydda i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder Aspose.Words för .NET för att skydda i word-dokument och endast tillåta att formulärfält redigeras.
type: docs
weight: 10
url: /sv/net/document-protection/allow-only-form-fields-protect/
---
Dokumentskydd är en viktig funktion vid ordbehandling med filer i din C#-applikation. Med Aspose.Words-biblioteket för .NET kan du enkelt skydda dina dokument och endast tillåta att formulärfält redigeras. I den här steg-för-steg-guiden går vi igenom hur du använder C#-källkod för att endast tillåta att formulärfält redigeras med funktionen Tillåt endast formulärfältskydd i Aspose.Words för .NET.

## Steg 1: Ställa in dokumentkatalogen

Det första steget är att definiera katalogen för ditt dokument. Du måste ange sökvägen där du vill spara det skyddade dokumentet. Till exempel :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: Infoga avsnitt och text

Därefter måste du infoga avsnitt och text i ditt dokument. Använd klassen DocumentBuilder från Aspose.Words för att bygga innehållet i ditt dokument. Här är ett enkelt exempel:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

I det här exemplet skapar vi ett nytt tomt dokument och använder sedan DocumentBuilder för att lägga till en textrad.

## Steg 3: Aktivera dokumentskydd

 Dokumentskydd fungerar bara när dokumentskydd är aktiverat. Du kan aktivera dokumentskydd med hjälp av`Protect` metoden för klassen Document. Här är hur:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

I det här exemplet aktiverar vi dokumentskydd genom att ange skyddstypen `

AllowOnlyFormFields` och ange ett lösenord.

## Steg 4: Tillåt endast formulärfält

Nu när dokumentskyddet är aktiverat måste vi specificera att endast redigering av formulärfält är tillåten. Detta säkerställer att användare endast kan redigera delar av dokumentet som är formulärfält. Här är hur:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Var noga med att ersätta "lösenord" med lösenordet du angav tidigare.

## Steg 5: Spara det skyddade dokumentet

Slutligen kan du spara det skyddade dokumentet med hjälp av`Save` metoden för klassen Document. Ange den fullständiga sökvägen och önskat filnamn. Till exempel :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Se till att ersätta "dataDir" med sökvägen till din dokumentkatalog.

### Exempel på källkod för funktionen Allow Only Form Fields Protect med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Infoga två avsnitt med lite text.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Ett dokumentskydd fungerar bara när dokumentskyddet är vänt och endast redigering i formulärfält är tillåten.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Spara det skyddade dokumentet.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Slutsats

I den här guiden utforskade vi hur man använder Aspose.Words-biblioteket för .NET för att skydda ett dokument och endast tillåta att formulärfält redigeras. Genom att följa de angivna stegen kan du enkelt implementera denna funktion i din C#-applikation. Dokumentskydd är viktigt för att säkerställa säkerheten och sekretessen för dina dokument.

### Vanliga frågor för att tillåta endast formulärfält skyddar i word-dokument

#### F: Vad är dokumentskydd i Aspose.Words för .NET?

S: Dokumentskydd i Aspose.Words för .NET är en funktion som låter dig säkra dina dokument genom att begränsa vissa åtgärder, såsom redigering, formatering eller innehållsändring. Det hjälper till att upprätthålla integriteten och sekretessen för dina dokument genom att förhindra obehöriga ändringar.

#### F: Hur kan jag skydda ett dokument och tillåta att endast formulärfält redigeras med Aspose.Words för .NET?

S: För att skydda ett dokument och tillåta att endast formulärfält redigeras med Aspose.Words för .NET, kan du följa dessa steg:
1. Definiera katalogsökvägen för ditt dokument.
2.  Infoga avsnitt och text i ditt dokument med hjälp av`DocumentBuilder` klass.
3.  Aktivera dokumentskydd med hjälp av`Protect` metod för`Document` klass, med angivande av skyddstyp som`AllowOnlyFormFields` och tillhandahålla ett lösenord.
4.  Spara det skyddade dokumentet med hjälp av`Save` metod för`Document` klass.

#### F: Kan jag infoga formulärfält i ett skyddat dokument med Aspose.Words för .NET?

S: Ja, du kan infoga formulärfält i ett skyddat dokument med Aspose.Words för .NET. Dokumentskyddet med`AllowOnlyFormFields` typ tillåter användare att endast redigera formulärfälten samtidigt som resten av dokumentets innehåll skyddas. Du kan använda`DocumentBuilder` klass för att infoga formulärfält i dokumentet innan skyddet aktiveras.

#### F: Kan jag ta bort dokumentskyddet från ett skyddat dokument?

 S: Ja, du kan ta bort dokumentskydd från ett skyddat dokument med Aspose.Words för .NET. För att ta bort skyddet kan du använda`Unprotect` metod för`Document` klass och ange rätt lösenord. Detta tar bort skyddet och tillåter obegränsad redigering av dokumentet.

#### F: Är det möjligt att skydda ett dokument med flera skyddstyper?

 S: Nej, Aspose.Words för .NET tillåter endast en skyddstyp att tillämpas på ett dokument åt gången. Men den`AllowOnlyFormFields` skyddstyp kan effektivt begränsa redigering till formulärfält samtidigt som andra skyddstyper, som t.ex`AllowOnlyComments` eller`AllowOnlyRevisions`att kombineras med formulärfältsskydd.

#### F: Kan jag ställa in olika lösenord för olika skyddstyper i ett dokument?

S: Nej, Aspose.Words för .NET låter dig ställa in ett enda lösenord för dokumentskydd, oavsett skyddstyp. Samma lösenord kommer att användas för att aktivera och inaktivera dokumentskydd.