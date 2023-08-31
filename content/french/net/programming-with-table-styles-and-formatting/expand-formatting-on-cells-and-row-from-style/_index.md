---
title: Développer le formatage des cellules et des lignes à partir du style
linktitle: Développer le formatage des cellules et des lignes à partir du style
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour étendre la mise en forme aux cellules et aux lignes à partir d'un style de tableau à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

Dans ce didacticiel, nous vous guiderons pas à pas à travers le processus permettant d'étendre la mise en forme aux cellules et aux lignes à partir d'un style utilisant Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment appliquer une mise en forme de style de tableau à des cellules et des lignes spécifiques de vos documents Word à l'aide d'Aspose.Words pour .NET.


## Étape 1 : Définir le répertoire des documents
Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. C'est ici que se trouve votre document Word. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Charger le document existant
 Ensuite, vous devez charger le document Word existant dans une instance du`Document` classe.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Étape 3 : Accédez à la première cellule du premier tableau
 Pour commencer, nous devons accéder à la première cellule du premier tableau du document. Nous utilisons le`GetChild()` et`FirstRow.FirstCell` méthodes pour obtenir la référence à la première cellule.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Étape 4 : Afficher le formatage initial des cellules
Avant de développer les styles du tableau, nous affichons la couleur d'arrière-plan actuelle de la cellule. Celui-ci doit être vide car le formatage actuel est stocké dans le style du tableau.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Étape 5 : Développez les styles de tableau pour un formatage direct
 Maintenant, nous étendons les styles de tableau pour diriger le formatage à l'aide du document`ExpandTableStylesToDirectFormatting()` méthode.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Étape 6 : Afficher le formatage des cellules après l'expansion du style
Nous affichons maintenant la couleur d'arrière-plan de la cellule après avoir développé les styles de tableau. Une couleur d'arrière-plan bleue doit être appliquée à partir du style de tableau.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Exemple de code source pour développer le formatage sur les cellules et la ligne à partir du style à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Obtenez la première cellule du premier tableau du document.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Imprimez d’abord la couleur de l’ombrage de la cellule.
	// Celui-ci doit être vide car l'ombrage actuel est stocké dans le style de tableau.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Imprimez maintenant l'ombrage des cellules après avoir développé les styles de tableau.
	// Une couleur de motif d'arrière-plan bleu aurait dû être appliquée à partir du style de tableau.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Conclusion
Dans ce didacticiel, nous avons appris à étendre la mise en forme aux cellules et aux lignes à partir d'un style de tableau à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement appliquer une mise en forme de style de tableau à des cellules et des lignes spécifiques de vos documents Word. Aspose.Words propose une API puissante et flexible pour manipuler et formater les tableaux de vos documents. Grâce à ces connaissances, vous pouvez personnaliser davantage la mise en page et la présentation de vos documents Word.