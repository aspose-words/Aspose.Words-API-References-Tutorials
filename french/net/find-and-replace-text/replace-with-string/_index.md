---
title: Remplacer par une chaîne
linktitle: Remplacer par une chaîne
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à remplacer du texte par une chaîne dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/find-and-replace-text/replace-with-string/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Remplacer par une chaîne dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet d'effectuer un remplacement de texte en fonction d'une chaîne de caractères spécifique dans un document Word.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Création d'un nouveau document

Avant de commencer à utiliser le remplacement de chaîne, nous devons créer un nouveau document en utilisant Aspose.Words pour .NET. Cela peut être fait en instanciant un`Document` objet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Étape 2 : Insérer du texte dans le document

 Une fois que nous avons un document, nous pouvons insérer du texte à l'aide d'un`DocumentBuilder` objet. Dans notre exemple, nous utilisons le`Writeln` méthode pour insérer la phrase "sad crazy bad":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Étape 3 : Remplacer par une chaîne

 Nous utilisons le`Range.Replace` méthode pour remplacer le texte par une chaîne. Dans notre exemple, nous remplaçons toutes les occurrences du mot "sad" par "bad" en utilisant le`FindReplaceOptions` possibilité avec le`FindReplaceDirection.Forward` sens de recherche :

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Étape 4 : Enregistrer le document modifié

 Enfin, nous enregistrons le document modifié dans un répertoire spécifié à l'aide de la`Save` méthode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Exemple de code source pour Remplacer par une chaîne en utilisant Aspose.Words pour .NET

Voici l'exemple de code source complet pour illustrer l'utilisation du remplacement par une chaîne de caractères avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Remplacer par une chaîne de Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour créer un document, insérer du texte, remplacer par une chaîne et enregistrer le document modifié.
