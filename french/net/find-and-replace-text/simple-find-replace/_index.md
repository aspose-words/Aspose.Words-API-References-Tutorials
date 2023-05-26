---
title: Recherche simple Remplacer
linktitle: Recherche simple Remplacer
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à effectuer une simple recherche de remplacement dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/find-and-replace-text/simple-find-replace/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Simple Find Replace dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet d'effectuer un simple remplacement de texte en recherchant une chaîne de caractères spécifique et en la remplaçant par une autre chaîne de caractères dans un document Word.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Création d'un nouveau document

 Avant de commencer à utiliser la recherche et le remplacement simples, nous devons créer un nouveau document en utilisant Aspose.Words pour .NET. Cela peut être fait en instanciant un`Document` objet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Étape 2 : Insérer du texte dans le document

 Une fois que nous avons un document, nous pouvons insérer du texte à l'aide d'un`DocumentBuilder` objet. Dans notre exemple, nous utilisons le`Writeln` méthode pour insérer la phrase "Bonjour_CustomerName_," :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Étape 3 : remplacement de texte simple

 Nous utilisons le`Range.Replace` méthode pour effectuer un remplacement de texte simple. Dans notre exemple, nous remplaçons toutes les occurrences de la chaîne "_ClientName_ " avec "James Bond" en utilisant le`FindReplaceOptions` possibilité avec le`FindReplaceDirection.Forward` sens de recherche :

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Étape 4 : Enregistrer le document modifié

 Enfin, nous enregistrons le document modifié dans un répertoire spécifié à l'aide de la`Save` méthode:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Exemple de code source pour Simple Find Replace utilisant Aspose.Words pour .NET

Voici l'exemple de code source complet pour illustrer l'utilisation de la recherche et du remplacement simples avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Enregistrer le document modifié
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Simple Find Replace de Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour créer un document, insérer du texte, effectuer un remplacement de texte simple et enregistrer le document modifié.
