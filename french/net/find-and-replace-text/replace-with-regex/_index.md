---
title: Remplacer par Regex
linktitle: Remplacer par Regex
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à effectuer un remplacement de texte basé sur une expression régulière dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/find-and-replace-text/replace-with-regex/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Remplacer par Regex dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet d'effectuer un remplacement de texte en fonction de modèles spécifiques définis par une expression régulière.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Création d'un nouveau document

 Avant de commencer à utiliser le remplacement des expressions régulières, nous devons créer un nouveau document en utilisant Aspose.Words pour .NET. Cela peut être fait en instanciant un`Document` objet:

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

## Étape 3 : Configuration des options de recherche et de remplacement

 Nous allons maintenant configurer les options de recherche et de remplacement à l'aide d'un`FindReplaceOptions` objet. Dans notre exemple, nous utilisons les options par défaut :

```csharp
FindReplaceOptions options = new FindReplaceOptions();
```

## Étape 4 : Remplacer par une expression régulière

 Nous utilisons le`Range.Replace` méthode pour effectuer un remplacement de texte à l'aide d'une expression régulière. Dans notre exemple, nous utilisons l'expression régulière "[s|m]ad" to find the words "sad" and "mad" and replace them with the word "bad":

```csharp
doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);
```

## Étape 5 : Enregistrer le document modifié

 Enfin, nous enregistrons le document modifié dans un répertoire spécifié à l'aide de la`Save` méthode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
```

### Exemple de code source pour Remplacer par Regex en utilisant Aspose.Words pour .NET

Voici l'exemple de code source complet pour démontrer l'utilisation du remplacement d'expression régulière avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	FindReplaceOptions options = new FindReplaceOptions();

	doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
  
```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Remplacer par Regex de Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour créer un document, insérer du texte, effectuer le remplacement par une expression régulière et enregistrer le document modifié.
