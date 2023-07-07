---
title: Infoga Mail Merge Address Block Field med DOM
linktitle: Infoga Mail Merge Address Block Field med DOM
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar ett blockeringsfält för e-postsammanslagning i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Infoga Mail Merge Address Block Field" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa Document and DocumentBuilder

Vi börjar med att skapa ett nytt dokument och initiera en DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Flytta markören till stycket

 Vi använder DocumentBuilder's`MoveTo()` metod för att flytta markören till stycket där vi vill infoga fältet för kopplingsadressblock.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Steg 4: Infoga fältet Mail Merge Address Block

 Vi använder DocumentBuilder's`InsertField()` metod för att infoga ett blockeringsfält för e-postsammanslagning i stycket.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Vi konfigurerar sedan egenskaperna för adressblockfältet och anger lämpliga alternativ, som att inkludera lands-/regionnamn, formatering av adressen enligt land/region, uteslutna lands-/regionnamn, namn- och adressformat och språkidentifierare.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Slutligen kallar vi`Update()` metod för att uppdatera fältet.

```csharp
field. Update();
```

### Exempel på källkod för att infoga ett fält för kopplingsadressblock med Aspose.Words för .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Vi vill infoga ett kopplingsadressblock så här:
// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { ADRESSBLOCK \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { ADRESSBLOCK \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { ADRESSBLOCK \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { ADRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### FAQ's

#### F: Hur kan jag anpassa formatet på postadressen i ett Word-dokument med Aspose.Words för .NET?

 S: Du kan anpassa formatet för postadressen i ett Word-dokument med Aspose.Words för .NET med hjälp av egenskaperna för`FieldAddressBlock`objekt. Du kan ställa in formateringsalternativ som adressstil, avgränsare, valfria objekt etc. för att få önskat format.

#### F: Hur kan jag ange källdata för postadressfältet i Aspose.Words för .NET?

 S: För att ange källdata för postadressfältet i Aspose.Words för .NET kan du använda`FieldAddressBlock.StartAddress` och`FieldAddressBlock.EndAddress` egenskaper. Dessa egenskaper används för att definiera adressintervallen i den externa datakällan, såsom en CSV-fil, databas, etc.

#### F: Kan jag inkludera valfria element i postadressfältet med Aspose.Words för .NET?

 S: Ja, du kan inkludera valfria element i postadressfältet med Aspose.Words för .NET. Du kan definiera valfria element genom att använda`FieldAddressBlock.OmitOptional` metod för att ange om valfria element som mottagarens namn, företagsnamn, etc. ska inkluderas eller exkluderas.

#### F: Påverkar Word-dokumentstrukturen med Aspose.Words för .NET om du infogar ett postadressfält med DOM?

S: Att infoga ett postadressfält med hjälp av DOM påverkar inte strukturen i Word-dokumentet direkt. Det lägger dock till ett nytt fältelement till dokumentinnehållet. Du kan manipulera dokumentstrukturen genom att lägga till, ta bort eller ändra befintliga element enligt dina behov.