---
title: Reconnaître et substitutions dans les modèles de remplacement
linktitle: Reconnaître et substitutions dans les modèles de remplacement
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser des modèles de remplacement avec des reconnaissances et des substitutions dans Aspose.Words pour .NET pour manipuler des documents Word.
type: docs
weight: 10
url: /fr/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

Dans cet article, nous allons explorer le code source C # ci-dessus pour comprendre comment utiliser la fonction de reconnaissance et de substitution dans les modèles de remplacement dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité aide à reconnaître les modèles de recherche complexes et à effectuer des substitutions en fonction des groupes capturés lors de la manipulation du document.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Création d'un nouveau document

 Avant de commencer à utiliser des correspondances et des substitutions dans les modèles de remplacement, nous devons créer un nouveau document en utilisant Aspose.Words pour .NET. Cela peut être fait en instanciant un`Document` objet:

```csharp
Document doc = new Document();
```

## Étape 2 : Insérer du texte dans le document

 Une fois que nous avons un document, nous pouvons insérer du texte à l'aide d'un`DocumentBuilder`objet. Dans notre exemple, nous utilisons le`Write` méthode pour insérer la phrase "Jason donne de l'argent à Paul". :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Étape 3 : Reconnaissances et substitutions dans les modèles de remplacement

 Nous allons maintenant utiliser le`Range.Replace` fonction pour effectuer une recherche et un remplacement de texte à l'aide d'une expression régulière pour reconnaître des modèles spécifiques. Dans notre exemple, nous utilisons l'expression régulière`([A-z]+) gives money to ([A-z]+)` reconnaître les phrases où quelqu'un donne de l'argent à quelqu'un d'autre. Nous utilisons le modèle de remplacement`$2 takes money from $1` effectuer la substitution en inversant les rôles. L'utilisation de`$1` et`$2` fait référence aux groupes capturés par l'expression régulière :

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Exemple de code source pour la reconnaissance et les substitutions dans les modèles de remplacement à l'aide de Aspose.Words pour .NET

Voici l'exemple de code source complet pour illustrer l'utilisation des correspondances et des substitutions dans les modèles de remplacement avec Aspose.Words pour .NET :

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonctionnalité de reconnaissance et de substitution dans les modèles de remplacement d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour créer un document, insérer du texte, effectuer une recherche et remplacer à l'aide d'expressions régulières et de modèles de substitution basés sur des groupes capturés, et manipuler le document.
