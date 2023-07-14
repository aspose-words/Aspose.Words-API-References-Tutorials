---
title: Obtenir la position de la table flottante
linktitle: Obtenir la position de la table flottante
second_title: API de traitement de documents Aspose.Words
description: Apprenez à obtenir la position des tableaux flottants dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/get-floating-table-position/
---

Dans ce didacticiel, nous allons apprendre à obtenir la position d'un tableau flottant dans un document Word à l'aide de Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure d'obtenir par programmation les propriétés de positionnement d'un tableau flottant dans vos documents Word.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Etape 2 : Charger le document et accéder aux tableaux
Pour démarrer le traitement de texte avec des tableaux, nous devons charger le document qui les contient et y accéder. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents. Assurez-vous également que le document contient des tableaux flottants.

## Étape 3 : Obtenir les propriétés de positionnement du tableau flottant
Ensuite, nous allons parcourir tous les tableaux du document et obtenir les propriétés de positionnement des tableaux flottants. Utilisez le code suivant :

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Si le tableau est de type flottant, imprimez ses propriétés de positionnement.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Ici, nous utilisons un`foreach` loop pour parcourir tous les tableaux du document. Nous vérifions si le tableau est de type flottant en vérifiant le`TextWrapping` propriété. Si tel est le cas, nous imprimons les propriétés de positionnement de la table, telles que l'ancre horizontale, l'ancre verticale, les distances horizontales et verticales absolues, l'autorisation de chevauchement, la distance horizontale absolue et l'alignement vertical relatif.
 
### Exemple de code source pour Get Floating Table Position à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Si le tableau est de type flottant, imprimez ses propriétés de positionnement.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Conclusion
Dans ce didacticiel, nous avons appris à obtenir la position d'un tableau flottant dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez obtenir par programme les propriétés de positionnement des tableaux flottants dans vos documents Word. Cette fonctionnalité vous permet d'analyser et de manipuler des tableaux flottants en fonction de vos besoins spécifiques.