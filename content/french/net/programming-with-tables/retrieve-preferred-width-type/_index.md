---
title: Récupérer le type de largeur préféré
linktitle: Récupérer le type de largeur préféré
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment récupérer le type et la valeur de largeur préférée d'une cellule dans un tableau Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/retrieve-preferred-width-type/
---

Dans ce didacticiel, nous apprendrons comment récupérer le type de largeur préféré et sa valeur à partir d'une cellule de tableau dans un document Word à l'aide d'Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. A la fin de ce didacticiel, vous pourrez récupérer le type de largeur préféré (absolu, relatif ou automatique) et sa valeur pour une cellule spécifique de vos tableaux de documents Word.

## Étape 1 : Configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : Chargement du document
Pour démarrer le traitement de texte avec le document, procédez comme suit :

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document
Document doc = new Document(dataDir + "Tables.docx");
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre répertoire de documents et fournissez le nom de fichier correct.

## Étape 3 : Récupération du type et de la valeur de largeur préférés
Ensuite, nous récupérerons le type de largeur préféré et sa valeur pour une cellule spécifique du tableau. Utilisez le code suivant :

```csharp
// Récupérer le tableau
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Activer l'ajustement automatique des tables
table. AllowAutoFit = true;

//Récupérer la première cellule de la première ligne
Cell firstCell = table.FirstRow.FirstCell;

// Récupérer le type de largeur préféré et sa valeur
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

 Ici, nous utilisons le document pour récupérer la première table, puis nous activons l'ajustement automatique de la table avec le`AllowAutoFit` propriété. Ensuite on récupère la première cellule de la première ligne du tableau. A partir de cette cellule, nous pouvons récupérer le type de largeur préféré avec le`PreferredWidth.Type` propriété et sa valeur avec le`PreferredWidth.Value` propriété.

### Exemple de code source pour récupérer le type de largeur préféré à l’aide d’Aspose.Words pour .NET 

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Conclusion
Dans ce didacticiel, nous avons appris à récupérer le type de largeur préféré et sa valeur à partir d'une cellule de tableau dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez récupérer ces informations pour des cellules spécifiques de vos tableaux de documents Word.