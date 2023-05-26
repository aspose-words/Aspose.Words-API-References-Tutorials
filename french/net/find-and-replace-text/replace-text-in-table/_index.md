---
title: Remplacer le texte dans le tableau
linktitle: Remplacer le texte dans le tableau
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à remplacer du texte dans un tableau dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/find-and-replace-text/replace-text-in-table/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Remplacer le texte dans le tableau dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet de rechercher et de remplacer un texte spécifique dans un tableau d'un document Word.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Charger le document

 Avant de commencer à utiliser le remplacement de texte dans un tableau, nous devons charger le document dans Aspose.Words pour .NET. Ceci peut être fait en utilisant le`Document` class et en spécifiant le chemin du fichier de document :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

## Étape 2 : Accéder au tableau

 Une fois le document chargé, nous devons naviguer vers la table où nous voulons effectuer le remplacement de texte. Dans notre exemple, nous utilisons le`GetChild` méthode avec la`NodeType.Table` paramètre pour obtenir le premier tableau du document :

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Étape 3 : Effectuer le remplacement du texte

 Maintenant, nous utilisons le`Range.Replace` méthode pour effectuer le remplacement de texte dans le tableau. Dans notre exemple, nous remplaçons toutes les occurrences du mot "Carrots" par "Eggs" en utilisant le`FindReplaceOptions` possibilité avec le`FindReplaceDirection.Forward` sens de recherche. De plus, nous remplaçons la valeur "50" par "20" dans la dernière cellule de la dernière ligne du tableau :

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Étape 4 : Enregistrer le document modifié

 Enfin, nous enregistrons le document modifié dans un répertoire spécifié à l'aide de la`Save` méthode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
```

Aspose.Words pour .NET Nous avons suivi un guide étape par étape pour charger un document, accéder à la table, effectuer le remplacement du texte et enregistrer le document modifié.

### Exemple de code source pour Remplacer le texte dans le tableau à l'aide de Aspose.Words pour .NET

Voici l'exemple de code source complet pour illustrer l'utilisation du remplacement de texte dans une table avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Tables.docx");

	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
	table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
    
```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Remplacer le texte dans le tableau d'Aspose.
