---
title: Mise en page dans la cellule
linktitle: Mise en page dans la cellule
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à mettre en page une forme dans une cellule de tableau dans un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/layout-in-cell/
---

Ce didacticiel explique comment mettre en page une forme dans une cellule de tableau dans un document Word à l'aide de Aspose.Words pour .NET. En ajustant les propriétés de la forme et en utilisant les options de mise en page, vous pouvez contrôler le positionnement et l'apparence de la forme dans la cellule.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et travail avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin d'accès réel au répertoire où vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document et DocumentBuilder
 Créez une nouvelle instance de`Document` classe et une`DocumentBuilder` objet de travailler avec le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Créer le tableau
 Utilisez le`StartTable`, `EndTable`, `InsertCell` , et`Write` méthodes de la`DocumentBuilder` objet pour construire une table. Définissez la hauteur de ligne et la règle de hauteur souhaitées à l'aide des`RowFormat` propriétés.

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
 Créer un`Shape` objet et configurez ses propriétés pour définir le filigrane. Définissez la forme à disposer dans une cellule à l'aide de la`IsLayoutInCell` propriété.

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

## Étape 5 : Personnalisez la forme
 Personnalisez l'apparence et le texte de la forme du filigrane en définissant des propriétés telles que`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`etc.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Étape 6 : Insérez la forme dans le document
 Insérez la forme du filigrane dans le document à l'aide du`InsertNode` méthode de la`DocumentBuilder` objet. Positionnez la forme à l'aide de la`MoveTo` méthode pour le placer après la dernière exécution dans le document.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Étape 7 : Enregistrer le document
 Enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithShapes.LayoutInCell.docx".

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### Exemple de code source pour Layout In Cell en utilisant Aspose.Words pour .NET 

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
		IsLayoutInCell = true, // Affichez la forme en dehors de la cellule du tableau si elle sera placée dans une cellule.
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

C'est ça! Vous avez réussi à disposer une forme dans une cellule de tableau dans un document Word à l'aide de Aspose.Words pour .NET.