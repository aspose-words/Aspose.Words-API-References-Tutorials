---
title: Modifier le formatage des lignes
linktitle: Modifier le formatage des lignes
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour modifier le formatage des lignes du tableau à l’aide d’Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus étape par étape pour modifier le formatage d'une ligne de tableau à l'aide d'Aspose.Words for .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment modifier les bordures, la hauteur et le saut de ligne d'une ligne de tableau dans vos documents Word à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. C'est ici que se trouve votre document Word. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Charger le document existant
 Ensuite, vous devez charger le document Word existant dans une instance du`Document` classe.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Étape 3 : Accédez à la ligne à modifier
 Pour modifier le formatage d'une ligne du tableau, nous devons accéder à la ligne spécifique du tableau. Nous utilisons le`GetChild()`et`FirstRow` méthodes pour obtenir la référence à la première ligne du tableau.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## Étape 4 : Modifier le formatage des lignes
 Nous pouvons maintenant modifier le formatage des lignes en utilisant les propriétés du`RowFormat` classe. Par exemple, nous pouvons supprimer les bordures de ligne, définir la hauteur automatique et autoriser les sauts de ligne.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Exemple de code source pour modifier le formatage des lignes à l’aide d’Aspose.Words for .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Récupérez la première ligne du tableau.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## Conclusion
Dans ce didacticiel, nous avons appris à modifier le formatage d'une ligne de tableau à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pouvez facilement ajuster les bordures, la hauteur et les sauts de ligne des lignes de vos tableaux dans vos documents Word. Aspose.Words propose une API puissante et flexible pour manipuler et formater les tableaux de vos documents. Grâce à ces connaissances, vous pouvez personnaliser la disposition visuelle de vos tables selon vos besoins spécifiques.