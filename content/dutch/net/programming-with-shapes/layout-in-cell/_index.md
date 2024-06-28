---
title: Indeling in cel
linktitle: Indeling in cel
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een vorm in een tabelcel in een Word-document kunt opmaken met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/layout-in-cell/
---

In deze zelfstudie wordt uitgelegd hoe u een vorm in een tabelcel in een Word-document kunt opmaken met behulp van Aspose.Words voor .NET. Door de vormeigenschappen aan te passen en de lay-outopties te gebruiken, kunt u de positionering en het uiterlijk van de vorm in de cel bepalen.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar u het document wilt opslaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een nieuw document en DocumentBuilder
 Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder` bezwaar maken tegen het werken met het document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Bouw de tafel
 Gebruik de`StartTable`, `EndTable`, `InsertCell` , En`Write` methoden van de`DocumentBuilder`object om een tafel te bouwen. Stel de gewenste rijhoogte en hoogteregel in met behulp van de`RowFormat` eigenschappen.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Stap 4: Maak en formatteer de vorm
 Maak een`Shape` object en configureer de eigenschappen ervan om het watermerk te definiëren. Stel de vorm in die binnen een cel moet worden opgemaakt met behulp van de`IsLayoutInCell` eigendom.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true,
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Stap 5: Pas de vorm aan
 Pas het uiterlijk en de tekst van de watermerkvorm aan door eigenschappen in te stellen, zoals`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`, enz.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Stap 6: Plaats de vorm in het document
 Voeg de watermerkvorm in het document in met behulp van de`InsertNode` werkwijze van de`DocumentBuilder` voorwerp. Positioneer de vorm met behulp van de`MoveTo` methode om deze na de laatste run in het document te plaatsen.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Stap 7: Bewaar het document
 Sla het document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithShapes.LayoutInCell.docx".

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### Voorbeeldbroncode voor Layout In Cell met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.RowFormat.Height = 100;
	builder.RowFormat.HeightRule = HeightRule.Exactly;
	for (int i = 0; i < 31; i++)
	{
		if (i != 0 && i % 7 == 0) builder.EndRow();
		builder.InsertCell();
		builder.Write("Cell contents");
	}
	builder.EndTable();
	Shape watermark = new Shape(doc, ShapeType.TextPlainText)
	{
		RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
		RelativeVerticalPosition = RelativeVerticalPosition.Page,
		IsLayoutInCell = true, // Geef de vorm buiten de tabelcel weer als deze in een cel wordt geplaatst.
		Width = 300,
		Height = 70,
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center,
		Rotation = -40
	};
	watermark.FillColor = Color.Gray;
	watermark.StrokeColor = Color.Gray;
	watermark.TextPath.Text = "watermarkText";
	watermark.TextPath.FontFamily = "Arial";
	watermark.Name = $"WaterMark_{Guid.NewGuid()}";
	watermark.WrapType = WrapType.None;
	Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
	builder.MoveTo(run);
	builder.InsertNode(watermark);
	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
	doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

Dat is het! U hebt met succes een vorm in een tabelcel in een Word-document ingedeeld met Aspose.Words voor .NET.