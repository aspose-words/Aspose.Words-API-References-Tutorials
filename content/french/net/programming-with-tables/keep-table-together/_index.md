---
title: Gardez la table ensemble
linktitle: Gardez la table ensemble
second_title: API de traitement de documents Aspose.Words
description: Apprenez à conserver un tableau dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/keep-table-together/
---

Dans ce didacticiel, nous allons apprendre à conserver un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de conserver un tableau intact sans le diviser sur plusieurs pages de vos documents Word.

## Étape 1 : Configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Chargement du document et récupération du tableau
Pour démarrer le traitement de texte avec le tableau, nous devons charger le document et récupérer le tableau que nous souhaitons conserver ensemble. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Récupérer le tableau
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre répertoire de documents.

## Étape 3 : Activez l'option « KeepWithNext »
Pour conserver le tableau ensemble et éviter qu'il ne soit divisé sur plusieurs pages, nous devons activer l'option "KeepWithNext" pour chaque paragraphe du tableau, à l'exception des derniers paragraphes de la dernière ligne du tableau. Utilisez le code suivant :

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Ici, nous parcourons chaque cellule du tableau et activons l'option "KeepWithNext" pour chaque paragraphe de la cellule, à l'exception des derniers paragraphes de la dernière ligne du tableau.

## Étape 4 : Sauvegarde du document modifié
Enfin, nous devons enregistrer le document modifié avec le tableau maintenu ensemble. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Assurez-vous de spécifier le chemin et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour Keep Table Together à l’aide d’Aspose.Words for .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Nous devons activer KeepWithNext pour chaque paragraphe du tableau afin de l'empêcher de traverser une page,
	//à l'exception des derniers paragraphes de la dernière ligne du tableau.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à conserver un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez conserver un tableau intact et l'empêcher de se diviser sur plusieurs pages de vos documents. Cette fonctionnalité vous donne plus de contrôle sur l'apparence et la disposition de vos tableaux dans vos documents.