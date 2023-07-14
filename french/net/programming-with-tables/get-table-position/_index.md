---
title: Obtenir la position du tableau
linktitle: Obtenir la position du tableau
second_title: API de traitement de documents Aspose.Words
description: Apprenez à obtenir la position d'un tableau dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/get-table-position/
---

Dans ce didacticiel, nous allons apprendre à obtenir la position d'un tableau dans un document Word à l'aide de Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure d'obtenir par programmation les propriétés de positionnement des tableaux dans vos documents Word.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Etape 2 : Chargement du document et accès au tableau
Pour démarrer le traitement de texte avec le tableau, nous devons charger le document qui le contient et y accéder. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Tables.docx");

// Accéder au tableau
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents. Assurez-vous également que le document contient la table dont vous souhaitez obtenir la position.

## Étape 3 : Obtenir les propriétés de positionnement du tableau
Ensuite, nous allons vérifier le type de positionnement du tableau et obtenir les propriétés de positionnement appropriées. Utilisez le code suivant :

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

 Ici, nous utilisons une condition pour vérifier si le tableau est de type flottant. Si c'est le cas, nous imprimons le`RelativeHorizontalAlignment` et`RelativeVerticalAlignment` properties pour obtenir l'alignement horizontal et vertical relatif du tableau. Sinon, nous imprimons le`Alignment` propriété pour obtenir l'alignement du tableau.

### Exemple de code source pour Get Table Position à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
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
Dans ce didacticiel, nous avons appris à obtenir la position d'un tableau dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez obtenir par programmation des propriétés de positionnement de tableau dans vos documents Word. Cette fonction vous permet d'analyser et de manipuler des tableaux en fonction de leurs positions spécifiques.