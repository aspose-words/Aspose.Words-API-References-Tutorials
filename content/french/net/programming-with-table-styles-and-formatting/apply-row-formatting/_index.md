---
title: Appliquer le formatage des lignes
linktitle: Appliquer le formatage des lignes
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour appliquer le formatage des lignes à un tableau à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

Dans ce didacticiel, nous vous expliquerons étape par étape le processus d'application de la mise en forme des lignes à une table à l'aide de Aspose.Words pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous comprendrez clairement comment formater les lignes de tableau dans vos documents Word à l'aide d'Aspose.Words pour .NET.

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

## Étape 3 : Démarrer un nouveau tableau
 Pour appliquer le formatage des lignes, nous devons d'abord commencer une nouvelle table en utilisant le`StartTable()` méthode du constructeur de document.

```csharp
Table table = builder. StartTable();
```

## Étape 4 : Insérer une cellule et passer au format de ligne
Nous pouvons maintenant insérer une cellule dans le tableau et accéder au format de ligne de cette cellule à l'aide du générateur de document`InsertCell()` et`RowFormat` méthodes.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Étape 5 : Définir la hauteur de ligne
 Pour définir la hauteur de ligne, nous utilisons le`Height` et`HeightRule` propriétés du format de ligne. Dans cet exemple, nous définissons une hauteur de ligne de 100 points et utilisons la`Exactly` règle.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Étape 6 : Définir la mise en forme du tableau
 Certaines propriétés de formatage peuvent être définies sur le tableau lui-même et sont appliquées à toutes les lignes du tableau. Dans cet exemple, nous définissons les propriétés de marge du tableau à l'aide de la propriété`LeftPadding`, `RightPadding`, `TopPadding` et`BottomPadding` propriétés.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Étape 7 : Ajouter du contenu à la ligne
Maintenant nous pouvons

 Nous allons ajouter du contenu à la ligne en utilisant les méthodes du constructeur de document. Dans cet exemple, nous utilisons le`Writeln()` méthode pour ajouter du texte à la ligne.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Étape 8 : Terminez la ligne et le tableau
 Une fois que nous avons ajouté le contenu à la ligne, nous pouvons terminer la ligne en utilisant le`EndRow()` méthode, puis terminez la table en utilisant la`EndTable()` méthode.

```csharp
builder. EndRow();
builder. EndTable();
```

## Étape 9 : Enregistrez le document modifié
Enfin, nous enregistrons le document modifié dans un fichier. Vous pouvez choisir un nom et un emplacement appropriés pour le document de sortie.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Félicitation ! Vous avez maintenant appliqué la mise en forme des lignes à une table à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Apply Row Formatting à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à appliquer la mise en forme des lignes à une table à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement intégrer cette fonctionnalité dans vos projets C#. La manipulation du formatage des lignes de tableau est un aspect essentiel du traitement des documents, et Aspose.Words propose une API puissante et flexible pour y parvenir. Grâce à ces connaissances, vous pouvez améliorer la présentation visuelle de vos documents Word et répondre à des exigences spécifiques.