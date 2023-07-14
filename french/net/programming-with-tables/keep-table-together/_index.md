---
title: Gardez la table ensemble
linktitle: Gardez la table ensemble
second_title: API de traitement de documents Aspose.Words
description: Apprenez à maintenir un tableau ensemble dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/keep-table-together/
---

Dans ce didacticiel, nous allons apprendre à maintenir un tableau dans un document Word à l'aide de Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous pourrez conserver un tableau intact sans le fractionner sur plusieurs pages de vos documents Word.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Etape 2 : Chargement du document et récupération du tableau
Pour démarrer le traitement de texte avec le tableau, nous devons charger le document et récupérer le tableau que nous voulons conserver ensemble. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Récupérer le tableau
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 3 : Activez l'option "KeepWithNext"
Pour garder le tableau ensemble et l'empêcher de se diviser sur plusieurs pages, nous devons activer l'option "KeepWithNext" pour chaque paragraphe du tableau, à l'exception des derniers paragraphes de la dernière ligne du tableau. Utilisez le code suivant :

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

## Étape 4 : Enregistrer le document modifié
Enfin, nous devons enregistrer le document modifié avec le tableau maintenu ensemble. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour Keep Table Together en utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Nous devons activer KeepWithNext pour chaque paragraphe du tableau pour l'empêcher de se briser sur une page,
	// sauf pour les derniers paragraphes de la dernière ligne du tableau.
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
Dans ce didacticiel, nous avons appris à conserver un tableau dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez conserver un tableau intact et l'empêcher de se diviser sur plusieurs pages dans vos documents. Cette fonctionnalité vous donne plus de contrôle sur l'apparence et la disposition de vos tableaux dans vos documents.