---
title: Comparer les options
linktitle: Comparer les options
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour expliquer le code source C# de la fonctionnalité Options de comparaison avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/compare-documents/compare-options/
---

Dans ce didacticiel, nous expliquerons comment utiliser la fonctionnalité Comparer les options avec Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications.

## Étape 1 : Comparer des documents avec des options personnalisées

 Pour commencer, chargez deux documents à comparer. Dans cet exemple, nous utiliserons le`Clone()` méthode pour créer une copie du document original. Voici comment:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Étape 2 : Configurer les options de comparaison

 Nous allons maintenant configurer les options de comparaison en créant un`CompareOptions` objet et en définissant les différentes propriétés selon les besoins. Voici comment:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Étape 3 : Comparer des documents avec des options personnalisées

 Nous allons maintenant utiliser le`Compare()` méthode passant les options personnalisées pour comparer les deux documents. Cette méthode marquera les changements dans le document d'origine. Voici comment:

```csharp
// Comparer des documents avec des options personnalisées
docA.Compare(docB, "user", DateTime.Now, options);

// Vérifiez si les documents sont égaux
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Exemple de code source pour les options de comparaison à l'aide de Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Comparer les options avec Aspose.Words pour .NET :

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Avec ce code, vous pouvez comparer deux documents en utilisant des options personnalisées pour ignorer des éléments spécifiques lors de la comparaison avec Aspose.Words pour .NET.

