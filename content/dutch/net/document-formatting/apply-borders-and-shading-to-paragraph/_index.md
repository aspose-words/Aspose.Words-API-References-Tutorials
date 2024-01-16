---
title: Randen en arcering toepassen op alinea's in Word-document
linktitle: Randen en arcering toepassen op alinea's in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u randen en arcering toepast op een alinea in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
In deze zelfstudie laten we u zien hoe u randen en arcering toepast op een alinea in een Word-document met behulp van de functionaliteit van Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en opmaakwijzigingen toe te passen.

## Stap 1: Het document aanmaken en configureren

Maak om te beginnen een nieuw document en een bijbehorend DocumentBuilder-object. Hier is hoe:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Randconfiguratie

Laten we nu de alinearanden configureren door de randstijl voor elke zijde op te geven. Hier is hoe:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Stap 3: Infill-installatie

We gaan nu de alinea-opvulling configureren door de textuur en de opvulkleuren op te geven. Hier is hoe:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Stap 4: Voeg inhoud toe

We gaan wat opgemaakte inhoud aan de paragraaf toevoegen. Hier is hoe:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Stap 3: Het document opslaan

 Nadat u het tekstinvoerformulierveld hebt ingevoegd, slaat u het document op de gewenste locatie op met behulp van de`Save` methode. Zorg ervoor dat u het juiste bestandspad opgeeft:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Voorbeeldbroncode voor het toepassen van randen en arcering op alinea's met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie Randen en arcering toepassen op alinea met Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u randen en arcering kunt toepassen op een alinea in een Word-document met behulp van Aspose.Words voor .NET. Door de alinea's te configureren`Borders` En`Shading` eigenschappen konden we de randstijl, lijnkleur en vulkleur voor de alinea instellen. Aspose.Words voor .NET biedt krachtige opmaakmogelijkheden om het uiterlijk van alinea's aan te passen en de visuele weergave van uw documenten te verbeteren.

### Veelgestelde vragen

#### Vraag: Hoe pas ik randen en arcering toe op een alinea in een Word-document met Aspose.Words voor .NET?

A: Volg deze stappen om randen en arcering toe te passen op een alinea in een Word-document met Aspose.Words voor .NET:
1.  Maak een nieuw document en a`DocumentBuilder` voorwerp.
2.  Configureer de alinearanden door naar het bestand te gaan`Borders` eigendom van de`ParagraphFormat` en het instellen van de randstijl voor elke zijde.
3.  Configureer de alinea-opvulling door naar het bestand te gaan`Shading` eigendom van de`ParagraphFormat` en het specificeren van de textuur en opvulkleuren.
4.  Voeg inhoud toe aan de alinea met behulp van de`Write` werkwijze van de`DocumentBuilder`.
5.  Sla het document op met behulp van de`Save` methode.

#### Vraag: Hoe stel ik de randstijl in voor elke zijde van de alinea?

 A: Om de randstijl voor elke zijde van de alinea in te stellen, kunt u toegang krijgen tot de`Borders` eigendom van de`ParagraphFormat` en stel de`LineStyle` eigendom voor ieder`BorderType` (bijv.`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). U kunt verschillende lijnstijlen opgeven, zoals`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, enz.

#### Vraag: Hoe geef ik de textuur en opvulkleuren op voor de alinea-arcering?

 A: Om de textuur en opvulkleuren voor de alinea-arcering op te geven, kunt u toegang krijgen tot het`Shading` eigendom van de`ParagraphFormat` en stel de`Texture` eigenschap naar een gewenste textuurindex (bijv.`TextureIndex.TextureDiagonalCross` ). U kunt ook de`BackgroundPatternColor` En`ForegroundPatternColor` eigenschappen naar de gewenste kleuren met behulp van de`System.Drawing.Color` klas.