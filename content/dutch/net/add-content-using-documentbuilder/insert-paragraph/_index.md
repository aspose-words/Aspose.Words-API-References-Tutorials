---
title: Paragraaf invoegen in Word-document
linktitle: Paragraaf invoegen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u opgemaakte alinea's in Word-documenten kunt invoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/insert-paragraph/
---
In deze uitgebreide zelfstudie leert u hoe u alinea's in een Word-document kunt invoegen met Aspose.Words voor .NET. Wij begeleiden u door het proces en voorzien u van de benodigde C#-codefragmenten. Aan het einde van deze handleiding kunt u opgemaakte alinea's aan uw documenten toevoegen.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Maak een nieuw document en DocumentBuilder
Maak om te beginnen een nieuw document met behulp van de klasse Document en initialiseer een DocumentBuilder-object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Stel het lettertype en de opmaak in
Stel vervolgens de lettertype-eigenschappen en alinea-opmaak in met respectievelijk de objecten Font en ParagraphFormat:

```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## Stap 3: Voeg een alinea in
Nadat u het lettertype en de opmaak hebt ingesteld, gebruikt u de Writeln-methode van de DocumentBuilder-klasse om een hele alinea in te voegen:

```csharp
builder.Writeln("A whole paragraph.");
```

## Stap 4: Sla het document op
Nadat u de alinea hebt ingevoegd, slaat u het document op in een bestand met behulp van de Save-methode van de Document-klasse:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Voorbeeldbroncode voor het invoegen van een alinea met Aspose.Words voor .NET
Hier is de volledige broncode voor het invoegen van een alinea met Aspose.Words voor .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;

builder.Writeln("A whole paragraph.");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u opgemaakte alinea's in een Word-document kunt invoegen met behulp van Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u nu aangepaste alinea's met specifieke lettertypen, opmaak en uitlijning aan uw documenten toevoegen.

### Veelgestelde vragen over het invoegen van een alinea in een Word-document

#### Vraag: Kan ik meerdere alinea's met verschillende opmaak in hetzelfde document invoegen?

 A: Ja, u kunt meerdere alinea's met verschillende opmaak in hetzelfde document invoegen met behulp van Aspose.Words voor .NET. Pas eenvoudig de eigenschappen van het lettertype en de alinea-opmaak aan voordat u de`Writeln` methode voor elke paragraaf.

#### Vraag: Hoe kan ik de regelafstand en de inspringing voor de alinea's instellen?

 A: Aspose.Words voor .NET biedt opties om de regelafstand en inspringing voor alinea's in te stellen. U kunt de`LineSpacing` En`LeftIndent` eigenschappen van de`ParagraphFormat` bezwaar maken tegen het beheersen van deze aspecten.

#### Vraag: Is het mogelijk om lijsten met opsommingstekens of genummerde lijsten in te voegen met DocumentBuilder?

 A: Ja, u kunt lijsten met opsommingstekens of genummerde lijsten maken door de`ListFormat` eigenschappen van de`DocumentBuilder` voorwerp. U kunt lijstitems toevoegen met behulp van de`Writeln` methode, en de nummering of opsommingstekenstijl wordt automatisch toegepast.

#### Vraag: Kan ik hyperlinks of andere elementen in de paragrafen invoegen?

 EEN: Absoluut! U kunt hyperlinks, afbeeldingen en andere elementen in de alinea's invoegen met behulp van de`DocumentBuilder` klas. Hierdoor kunt u rijke en interactieve inhoud binnen uw paragrafen creëren.

#### Vraag: Hoe kan ik speciale tekens of symbolen in een alinea invoegen?

 A: Om speciale tekens of symbolen in te voegen, kunt u de`Writeln` methode met de gewenste Unicode-weergave of gebruik de`InsertSpecialChar` werkwijze van de`DocumentBuilder` klas.