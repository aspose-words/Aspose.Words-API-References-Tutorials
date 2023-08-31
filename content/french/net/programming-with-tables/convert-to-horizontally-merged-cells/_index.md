---
title: Convertir en cellules fusionnées horizontalement
linktitle: Convertir en cellules fusionnées horizontalement
second_title: API de traitement de documents Aspose.Words
description: Apprenez à convertir des cellules de tableau en cellules fusionnées horizontalement dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

Dans ce didacticiel, nous apprendrons à utiliser Aspose.Words pour .NET pour convertir des cellules de tableau en cellules fusionnées horizontalement dans un document Word. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de manipuler par programmation des cellules de tableau dans vos documents Word.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Etape 2 : Chargement du document et accès au tableau
Pour démarrer le traitement de texte avec le tableau, nous devons charger le document qui le contient et y accéder. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Accéder au tableau
Table table = doc.FirstSection.Body.Tables[0];
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents. Assurez-vous également que le document contient un tableau avec des cellules fusionnées horizontalement.

## Étape 3 : convertir en cellules fusionnées horizontalement
 Ensuite, nous allons convertir les cellules du tableau en cellules fusionnées horizontalement à l'aide de la`ConvertToHorizontallyMergedCells()` méthode. Utilisez le code suivant :

```csharp
// Convertir en cellules fusionnées horizontalement
table. ConvertToHorizontallyMergedCells();
```

 Ici, nous appelons simplement le`ConvertToHorizontallyMergedCells()` méthode sur le tableau pour effectuer la conversion.

### Exemple de code source pour Convertir en cellules fusionnées horizontalement à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Désormais, les cellules fusionnées ont les indicateurs de fusion appropriés.
	table.ConvertToHorizontallyMergedCells();
```

## Conclusion
Dans ce didacticiel, nous avons appris à convertir des cellules de tableau en cellules fusionnées horizontalement dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez manipuler par programmation des cellules de tableau dans vos documents Word. Cette fonctionnalité vous permet de gérer et d'organiser vos données de manière flexible et personnalisée dans un tableau.