---
title: Construire une table avec style
linktitle: Construire une table avec style
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour créer un tableau avec un style personnalisé à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

Dans ce didacticiel, nous vous guiderons pas à pas dans le processus de création d'un tableau stylisé à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment créer un tableau avec un style personnalisé dans vos documents Word à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document Word modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Créer un nouveau document et un générateur de documents
 Ensuite, vous devez créer une nouvelle instance de`Document` classe et un constructeur de document pour ce document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Commencez un nouveau tableau et insérez une cellule
 Pour commencer à construire la table, nous utilisons le`StartTable()` méthode du générateur de document, puis nous insérons une cellule dans le tableau à l'aide de la`InsertCell()` méthode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Étape 4 : Définir le style du tableau
 Nous pouvons maintenant définir le style de tableau à l'aide de la`StyleIdentifier` propriété. Dans cet exemple, nous utilisons le style "MediumShading1Accent1".

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Étape 5 : Appliquer les options de style au tableau
 Nous pouvons spécifier quelles caractéristiques doivent être formatées par le style en utilisant le`StyleOptions`propriété du tableau. Dans cet exemple, nous appliquons les options suivantes : "FirstColumn", "RowBands" et "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Étape 6 : Ajuster automatiquement la taille du tableau
 Pour ajuster automatiquement la taille du tableau en fonction de son contenu, nous utilisons le`AutoFit()` méthode avec la`AutoFitBehavior.AutoFitToContents` comportement.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Étape 7 : Ajouter du contenu aux cellules
 Maintenant, nous pouvons ajouter du contenu aux cellules en utilisant le`Writeln()` et`InsertCell()` méthodes du générateur de documents. Dans cet exemple, nous ajoutons les en-têtes pour "Item" et "Quantity (

kg)" et les données correspondantes.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## Étape 8 : Enregistrez le document modifié
Enfin, nous enregistrons le document modifié dans un fichier. Vous pouvez choisir un nom et un emplacement appropriés pour le document de sortie.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Félicitation ! Vous avez maintenant créé un tableau de style personnalisé à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Build Table With Style à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Nous devons d'abord insérer au moins une ligne avant de définir la mise en forme du tableau.
	builder.InsertCell();
	// Définissez le style de tableau utilisé en fonction de l'identificateur de style unique.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Appliquez les fonctionnalités qui doivent être formatées par le style.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à créer un tableau stylisé à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement personnaliser le style de vos tableaux dans vos documents Word. Aspose.Words offre une API puissante et flexible pour manipuler et formater des tableaux dans vos documents. Grâce à ces connaissances, vous pouvez améliorer la présentation visuelle de vos documents Word et répondre à des besoins spécifiques.