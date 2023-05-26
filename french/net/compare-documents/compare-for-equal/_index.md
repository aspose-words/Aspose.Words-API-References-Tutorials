---
title: Comparer pour égal
linktitle: Comparer pour égal
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour expliquer le code source C# de la fonctionnalité Compare for Equals avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/compare-documents/compare-for-equal/
---

Dans ce didacticiel, nous vous expliquerons comment utiliser la fonctionnalité Compare for Equal avec Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications.

## Étape 1 : Comparaison de documents

 Pour commencer, chargez deux documents à comparer. Dans cet exemple, nous utiliserons le`Clone()` méthode pour créer une copie du document original. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## Étape 2 : Comparaison de documents

 Nous allons maintenant utiliser le`Compare()` méthode pour comparer les deux documents. Cette méthode marquera les changements dans le document d'origine. Voici comment:

```csharp
// Comparez les documents
docA.Compare(docB, "user", DateTime.Now);

// Vérifiez si les documents sont égaux
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### Exemple de code source pour Compare For Equal en utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Compare for Equals avec Aspose.Words pour .NET :

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA contient désormais les modifications sous forme de révisions.
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Avec ce code, vous pourrez comparer deux documents et déterminer s'ils sont identiques en utilisant Aspose.Words pour .NET.

