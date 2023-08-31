---
title: Fusion verticale
linktitle: Fusion verticale
second_title: API de traitement de documents Aspose.Words
description: Apprenez à fusionner verticalement des cellules dans un tableau dans un document Word à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/vertical-merge/
---

Dans ce didacticiel, nous allons apprendre à fusionner verticalement des cellules dans un tableau dans un document Word à l'aide de Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous pourrez fusionner verticalement des cellules dans vos tableaux dans des documents Word.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Chargement du document
Pour démarrer le traitement de texte avec le document, procédez comme suit :

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer un nouveau document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 3 : Fusion verticale des cellules
Ensuite, nous fusionnerons les cellules verticalement dans le tableau. Utilisez le code suivant :

```csharp
// Insérer une cellule
builder. InsertCell();

// Appliquer la fusion verticale à la première cellule
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Insérer une autre cellule
builder. InsertCell();

// N'appliquer aucune fusion verticale à la cellule
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Insérer une cellule
builder. InsertCell();

// Appliquer la fusion verticale avec la cellule précédente
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Insérer une autre cellule
builder. InsertCell();

// N'appliquer aucune fusion verticale à la cellule
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Terminer la création de la table
builder. EndTable();
```

Dans ce code, nous utilisons le constructeur DocumentBuilder pour insérer des cellules dans un tableau. Nous appliquons la fusion verticale aux cellules à l'aide de la propriété CellFormat.VerticalMerge. Nous utilisons CellMerge.First pour la première fusion de cellules, CellMerge.Previous pour fusionner avec la cellule précédente et CellMerge.None pour aucune fusion verticale.

## Étape 4 : Enregistrer le document modifié
Enfin, nous devons enregistrer le document modifié avec les cellules fusionnées. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour la fusion verticale à l'aide d'Aspose.Words pour .NET 
```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Cette cellule est fusionnée verticalement avec la cellule du dessus et doit être vide.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à fusionner verticalement des cellules dans un tableau dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez facilement fusionner des cellules Vertical dans vos tableaux.