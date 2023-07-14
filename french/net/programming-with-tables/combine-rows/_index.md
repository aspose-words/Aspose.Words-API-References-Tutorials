---
title: Combiner les lignes
linktitle: Combiner les lignes
second_title: API de traitement de documents Aspose.Words
description: Apprenez à combiner des lignes de tableau dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/combine-rows/
---

Dans ce didacticiel, nous apprendrons à utiliser Aspose.Words pour .NET pour combiner des lignes de tableaux dans un document Word. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de manipuler et de fusionner par programmation des lignes de tableau dans vos documents Word.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Etape 2 : Charger le document et accéder aux tableaux
Pour démarrer le traitement de texte avec des tableaux, nous devons charger le document qui les contient et y accéder. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Tables.docx");

// Accéder aux tableaux
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 3 : Combiner les lignes du tableau
Ensuite, nous combinerons les lignes du deuxième tableau à la fin du premier tableau. Utilisez le code suivant :

```csharp
// Combinaison de lignes de tableau
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Ici, nous utilisons un`while` loop pour itérer sur toutes les lignes du deuxième tableau et les ajouter à la fin du premier tableau à l'aide de la`Add` méthode. Ensuite, nous supprimons le deuxième tableau du document à l'aide de la`Remove` méthode.

## Étape 4 : Enregistrer le document modifié
Enfin, nous devons enregistrer le document modifié avec les lignes de tableau combinées. Utilisez le code suivant :

```csharp
// Enregistrer le document modifié
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour combiner des lignes à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Les lignes du deuxième tableau seront ajoutées à la fin du premier tableau.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Ajouter toutes les lignes de la table actuelle aux tables suivantes
	// avec différents nombres et largeurs de cellules peuvent être réunis dans un seul tableau.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à combiner des lignes de tableaux dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez manipuler par programme les lignes de tableau dans vos documents Word. Cette fonctionnalité vous permet de fusionner et d'organiser efficacement vos données dans un tableau.