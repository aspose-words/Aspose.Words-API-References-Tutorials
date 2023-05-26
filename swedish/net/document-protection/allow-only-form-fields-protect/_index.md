---
title: Tillåt endast formulärfältsskydd
linktitle: Tillåt endast formulärfältsskydd
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder Aspose.Words för .NET för att skydda dokument och endast tillåta att formulärfält redigeras.
type: docs
weight: 10
url: /sv/net/document-protection/allow-only-form-fields-protect/
---

Dokumentskydd är en viktig funktion när du arbetar med filer i din C#-applikation. Med Aspose.Words-biblioteket för .NET kan du enkelt skydda dina dokument och endast tillåta att formulärfält redigeras. I den här steg-för-steg-guiden går vi igenom hur du använder C#-källkod för att endast tillåta att formulärfält redigeras med funktionen Tillåt endast formulärfältskydd i Aspose.Words för .NET.

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
