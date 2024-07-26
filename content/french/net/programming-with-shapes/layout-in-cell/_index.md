---
title: Disposition dans la cellule
linktitle: Disposition dans la cellule
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment disposer une forme dans une cellule de tableau dans un document Word à l’aide d’Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/layout-in-cell/
---

Ce didacticiel explique comment disposer une forme dans une cellule de tableau dans un document Word à l'aide d'Aspose.Words pour .NET. En ajustant les propriétés de la forme et en utilisant les options de disposition, vous pouvez contrôler le positionnement et l'apparence de la forme dans la cellule.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel du répertoire dans lequel vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document et DocumentBuilder
 Créez une nouvelle instance du`Document` classe et un`DocumentBuilder` s'opposer à travailler avec le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Construire la table
 Utilisez le`StartTable`, `EndTable`, `InsertCell` , et`Write` méthodes du`DocumentBuilder` objet pour construire une table. Définissez la hauteur de ligne souhaitée et la règle de hauteur à l'aide du`RowFormat` propriétés.

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

## Étape 4 : Créer et formater la forme
 Créer un`Shape` objet et configurez ses propriétés pour définir le filigrane. Définissez la forme à disposer dans une cellule à l'aide du`IsLayoutInCell` propriété.

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

## Étape 5 : Personnaliser la forme
 Personnalisez l'apparence et le texte de la forme du filigrane en définissant des propriétés telles que`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`, etc.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Étape 6 : Insérez la forme dans le document
 Insérez la forme du filigrane dans le document à l'aide du`InsertNode` méthode du`DocumentBuilder` objet. Positionnez la forme à l'aide du`MoveTo` méthode pour le placer après la dernière exécution dans le document.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Étape 7 : Enregistrez le document
 Enregistrez le document dans le répertoire spécifié à l'aide du`Save`méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithShapes.LayoutInCell.docx ».

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### Exemple de code source pour Layout In Cell utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
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
		IsLayoutInCell = true, // Affichez la forme à l'extérieur de la cellule du tableau si elle doit être placée dans une cellule.
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

C'est ça! Vous avez réussi à disposer une forme dans une cellule de tableau dans un document Word à l’aide d’Aspose.Words pour .NET.