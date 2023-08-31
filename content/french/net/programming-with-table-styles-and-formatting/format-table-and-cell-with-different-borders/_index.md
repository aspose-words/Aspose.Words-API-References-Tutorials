---
title: Formater le tableau et la cellule avec des bordures différentes
linktitle: Formater le tableau et la cellule avec des bordures différentes
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour formater un tableau et une cellule avec des bordures différentes à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

Dans ce didacticiel, nous vous guiderons pas à pas à travers le processus de formatage d'un tableau et d'une cellule avec des bordures différentes à l'aide d'Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment appliquer des bordures personnalisées à des tableaux et cellules spécifiques de vos documents Word à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. C'est l'emplacement où vous souhaitez enregistrer votre document Word modifié. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Créer un nouveau document et un générateur de documents
 Ensuite, vous devez créer une nouvelle instance du`Document` classe et un constructeur de document pour ce document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : créez un nouveau tableau et ajoutez des cellules
Pour commencer à créer le tableau, nous utilisons le`StartTable()` méthode du générateur de documents, puis nous ajoutons des cellules au tableau en utilisant la`InsertCell()` méthode et nous écrivons le contenu des cellules dans la méthode`Writeln()` méthode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Définissez des bordures pour l’ensemble du tableau.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Définissez le remplissage pour cette cellule.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// Spécifiez un remplissage de cellule différent pour la deuxième cellule.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Effacer le formatage des cellules des opérations précédentes.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Créez des bordures plus épaisses pour la première cellule de cette ligne. Ce sera différent
// par rapport aux bordures définies pour le tableau.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Étape 4 : Enregistrez le document

  modifié
Enfin, enregistrez le document modifié dans un fichier. Vous pouvez choisir un nom et un emplacement appropriés pour le document de sortie.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Félicitation ! Vous avez maintenant formaté un tableau et une cellule avec des bordures différentes à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour formater un tableau et une cellule avec différentes bordures à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Définissez les bordures de l'ensemble du tableau.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// Définissez l'ombrage de la cellule pour cette cellule.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// Spécifiez un ombrage de cellule différent pour la deuxième cellule.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// Effacez le formatage des cellules des opérations précédentes.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// Créez des bordures plus grandes pour la première cellule de cette ligne. Ce sera différent
	// par rapport aux bordures fixées pour la table.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à formater un tableau et une cellule avec des bordures différentes à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement personnaliser les bordures de votre tableau et de vos cellules dans vos documents Word. Aspose.Words propose une API puissante et flexible pour manipuler et formater les tableaux de vos documents. Grâce à ces connaissances, vous pourrez améliorer la présentation visuelle de vos documents Word et répondre à des besoins spécifiques.