---
title: Obtenir la position de la table
linktitle: Obtenir la position de la table
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment obtenir la position d'un tableau dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/get-table-position/
---

Dans ce tutoriel, nous allons apprendre comment obtenir la position d'un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous pourrez obtenir par programmation les propriétés de positionnement des tableaux dans vos documents Word.

## Étape 1 : Configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Chargement du document et accès au tableau
Pour démarrer le traitement de texte avec le tableau, nous devons charger le document qui le contient et y accéder. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Tables.docx");

// Accès au tableau
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre répertoire de documents. Assurez-vous également que le document contient le tableau dont vous souhaitez obtenir la position.

## Étape 3 : Obtenir les propriétés de positionnement du tableau
Ensuite, nous vérifierons le type de positionnement du tableau et obtiendrons les propriétés de positionnement appropriées. Utilisez le code suivant :

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Ici, nous utilisons une condition pour vérifier si le tableau est de type float. Si c'est le cas, nous imprimons le`RelativeHorizontalAlignment`et`RelativeVerticalAlignment` propriétés pour obtenir l’alignement horizontal et vertical relatif de la table. Sinon, nous imprimons le`Alignment` propriété pour obtenir l’alignement du tableau.

### Exemple de code source pour obtenir la position de la table à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Conclusion
Dans ce didacticiel, nous avons appris comment obtenir la position d'un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez obtenir par programme les propriétés de positionnement des tableaux dans vos documents Word. Cette fonctionnalité vous permet d'analyser et de manipuler des tableaux en fonction de leurs positions spécifiques.