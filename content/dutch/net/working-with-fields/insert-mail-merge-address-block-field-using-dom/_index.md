---
title: Voeg een samenvoegadresblokveld in met behulp van DOM
linktitle: Voeg een samenvoegadresblokveld in met behulp van DOM
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een adresblokveld voor samenvoegen kunt invoegen in uw Word-documenten met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functie "Insert Mail Merge Address Block Field" van Aspose.Words voor .NET. Zorg ervoor dat u elke stap zorgvuldig volgt om de gewenste resultaten te krijgen.

## Stap 1: Documentmap instellen

In de verstrekte code moet u de directory van uw documenten opgeven. Vervang de waarde "UW DOCUMENTENMAP" door het juiste pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document en DocumentBuilder maken

We beginnen met het maken van een nieuw document en het initialiseren van een DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Cursor naar alinea verplaatsen

 Wij gebruiken de DocumentBuilder`MoveTo()` methode om de cursor naar de alinea te verplaatsen waarin we het veld voor het samenvoegadresblok willen invoegen.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Stap 4: Het veld Afdruk samenvoegen adresblok invoegen

 Wij gebruiken de DocumentBuilder`InsertField()` methode om een veld voor een samenvoegadresblok in de alinea in te voegen.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Vervolgens configureren we de eigenschappen van het adresblokveld en specificeren we de juiste opties, zoals het opnemen van de land-/regionaam, het opmaken van het adres op basis van land/regio, uitgesloten land-/regionamen, naam- en adresnotatie en taalidentificatie.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Tenslotte noemen wij de`Update()` methode om het veld bij te werken.

```csharp
field. Update();
```

### Voorbeeldbroncode voor het invoegen van een adresblokveld voor samenvoegbewerkingen met Aspose.Words voor .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// We willen een samenvoegadresblok als volgt invoegen:
// { ADRESBLOK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { ADRESBLOK \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { ADRESBLOK \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { ADRESBLOK \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { ADRESBLOK \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { ADRESBLOK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### Veelgestelde vragen

#### Vraag: Hoe kan ik de indeling van het postadres in een Word-document aanpassen met Aspose.Words voor .NET?

 A: U kunt de indeling van het postadres in een Word-document aanpassen met Aspose.Words voor .NET met behulp van de eigenschappen van de`FieldAddressBlock`voorwerp. U kunt de opmaakopties instellen, zoals adresstijl, scheidingstekens, optionele items, enz. om het gewenste formaat te krijgen.

#### Vraag: Hoe kan ik de brongegevens voor het postadresveld in Aspose.Words voor .NET opgeven?

 A: Om de brongegevens voor het postadresveld in Aspose.Words voor .NET op te geven, kunt u de`FieldAddressBlock.StartAddress` En`FieldAddressBlock.EndAddress` eigenschappen. Deze eigenschappen worden gebruikt om de adresbereiken in de externe gegevensbron te definiëren, zoals een CSV-bestand, database, enz.

#### Vraag: Kan ik optionele elementen opnemen in het postadresveld met Aspose.Words voor .NET?

 A: Ja, u kunt optionele elementen opnemen in het postadresveld met Aspose.Words voor .NET. U kunt optionele elementen definiëren met behulp van de`FieldAddressBlock.OmitOptional` methode om op te geven of optionele elementen zoals de naam van de ontvanger, de bedrijfsnaam, enz. moeten worden opgenomen of uitgesloten.

#### Vraag: Heeft het invoegen van een postadresveld met behulp van de DOM invloed op de Word-documentstructuur met Aspose.Words voor .NET?

A: Het invoegen van een postadresveld met behulp van de DOM heeft geen directe invloed op de structuur van het Word-document. Het voegt echter een nieuw veldelement toe aan de documentinhoud. U kunt de documentstructuur manipuleren door de bestaande elementen toe te voegen, te verwijderen of te wijzigen, afhankelijk van uw behoeften.