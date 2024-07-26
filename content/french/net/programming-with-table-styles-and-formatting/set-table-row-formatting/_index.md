---
title: Définir le formatage des lignes du tableau
linktitle: Définir le formatage des lignes du tableau
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour définir le formatage des lignes d’un tableau à l’aide d’Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus étape par étape pour définir le formatage des lignes d'un tableau à l'aide d'Aspose.Words for .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment ajuster la hauteur et les remplissages d'une ligne de tableau dans vos documents Word à l'aide d'Aspose.Words pour .NET.

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

## Étape 3 : Démarrez un nouveau tableau et ajoutez une cellule
Pour commencer à créer le tableau, nous utilisons le`StartTable()` méthode du constructeur de document, puis on ajoute une cellule au tableau en utilisant la`InsertCell()` méthode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Étape 4 : Définir le formatage de la ligne
 Nous pouvons maintenant définir le formatage des lignes en accédant au`RowFormat` objet de la`DocumentBuilder` objet. Nous pouvons définir la hauteur de ligne et les marges (paddings) en utilisant les propriétés correspondantes.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Étape 5 : Définir les marges du tableau
 Ensuite, nous pouvons définir les remplissages du tableau en accédant aux propriétés correspondantes du`Table` objet. Ces marges seront appliquées à toutes les lignes du tableau.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Étape 6 : Ajouter du contenu à la ligne
 Enfin, nous pouvons ajouter du contenu à la ligne en utilisant le générateur de documents`Writeln()` méthode.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Étape 7 : Terminez le tableau et enregistrez le document
Dans

 fin, nous finissons de créer la table en utilisant le`EndRow()`et`EndTable()` méthode, puis nous enregistrons le document modifié dans un fichier.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Exemple de code source pour définir le formatage des lignes de tableau à l’aide d’Aspose.Words for .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Ces propriétés de mise en forme sont définies sur le tableau et sont appliquées à toutes les lignes du tableau.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir le formatage des lignes d'un tableau à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement ajuster la hauteur et les marges des lignes du tableau dans vos documents Word. Aspose.Words propose une API puissante et flexible pour manipuler et formater les tableaux de vos documents. Grâce à ces connaissances, vous pouvez personnaliser la disposition visuelle de vos tables selon vos besoins spécifiques.