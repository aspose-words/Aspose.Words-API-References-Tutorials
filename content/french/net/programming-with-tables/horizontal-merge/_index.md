---
title: Fusion horizontale
linktitle: Fusion horizontale
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment fusionner horizontalement des cellules dans un tableau Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/horizontal-merge/
---

Dans ce didacticiel, nous apprendrons comment fusionner horizontalement des cellules dans un tableau d'un document Word à l'aide d'Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de fusionner horizontalement des cellules dans vos tableaux Word par programmation.

## Étape 1 : Configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Création du document et initialisation du générateur de documents
Pour démarrer le traitement de texte avec le tableau et les cellules, nous devons créer un nouveau document et initialiser le générateur de document. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer le document et initialiser le générateur de documents
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre répertoire de documents.

## Étape 3 : Construire le tableau avec fusion horizontale de cellules
Ensuite, nous allons créer le tableau et appliquer la fusion horizontale de cellules à l'aide des propriétés fournies par Aspose.Words pour .NET. Utilisez le code suivant :

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Cette cellule est fusionnée avec la précédente et doit être vide.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Ici, nous utilisons le générateur de documents pour créer le tableau et définir les propriétés de fusion horizontale des cellules. Nous utilisons le`HorizontalMerge` propriété du`CellFormat` objet pour spécifier le type de fusion horizontale à appliquer à chaque cellule. En utilisant`CellMerge.First` on fusionne la première cellule avec la suivante, tout en utilisant`CellMerge.Previous` nous fusionnons la cellule actuelle avec la cellule précédente.`CellMerge.None` indique que la cellule ne doit pas être fusionnée.

## Étape 4 : Sauvegarde du document modifié
Enfin, nous devons enregistrer le document modifié avec les cellules fusionnées horizontalement. Utilisez le code suivant :

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Assurez-vous de spécifier le chemin et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour la fusion horizontale à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Cette cellule est fusionnée avec la précédente et doit être vide.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à fusionner horizontalement des cellules dans un tableau d'un document Word à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez appliquer par programme la fusion horizontale de cellules dans vos tableaux Word. Cette fonctionnalité vous permet de créer des mises en page de tableaux plus complexes et de mieux organiser vos données.