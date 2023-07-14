---
title: Reconnaître et substitutions dans les modèles de remplacement
linktitle: Reconnaître et substitutions dans les modèles de remplacement
second_title: API de traitement de documents Aspose.Words
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

 Une fois que nous avons un document, nous pouvons insérer du texte à l'aide d'un`DocumentBuilder` objet. Dans notre exemple, nous utilisons le`Write` méthode pour insérer la phrase "Jason donne de l'argent à Paul". :

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

### FAQ

#### Q : Qu'est-ce que la fonctionnalité "Reconnaître et remplacer les modèles de remplacement" dans Aspose.Words pour .NET ?

R : La fonctionnalité "Reconnaître et remplacer les modèles dans les modèles de remplacement" dans Aspose.Words pour .NET vous permet de reconnaître des modèles de recherche complexes à l'aide d'expressions régulières et d'effectuer des substitutions en fonction des groupes capturés lors de la manipulation du document. Il vous permet de transformer dynamiquement le texte correspondant en référençant les groupes capturés dans le modèle de remplacement.

#### Q : Comment puis-je créer un nouveau document en utilisant Aspose.Words pour .NET ?

 R : Pour créer un nouveau document à l'aide d'Aspose.Words pour .NET, vous pouvez instancier un`Document` objet. Voici un exemple de code C# pour créer un nouveau document :

```csharp
Document doc = new Document();
```

#### Q : Comment puis-je insérer du texte dans un document en utilisant Aspose.Words pour .NET ?

 R : Une fois que vous avez un document, vous pouvez insérer du texte à l'aide d'un`DocumentBuilder` objet. Par exemple, pour insérer la phrase "Jason donne de l'argent à Paul.", vous pouvez utiliser la`Write` méthode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### Q : Comment puis-je effectuer une recherche et un remplacement de texte à l'aide d'expressions régulières dans Aspose.Words pour .NET ?

 R : Pour effectuer une recherche et un remplacement de texte à l'aide d'expressions régulières dans Aspose.Words pour .NET, vous pouvez utiliser le`Range.Replace` fonction avec un modèle d'expression régulière. Vous pouvez créer un`Regex` objet avec le motif souhaité et passez-le au`Replace` méthode:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Q : Comment puis-je utiliser des groupes capturés dans le modèle de remplacement lors de la recherche et du remplacement de texte dans Aspose.Words pour .NET ?

 R : Pour utiliser des groupes capturés dans le modèle de remplacement lors de la recherche et du remplacement de texte dans Aspose.Words pour .NET, vous pouvez activer le`UseSubstitutions`propriété de la`FindReplaceOptions` objet. Cela vous permet de référencer les groupes capturés en utilisant`$1`, `$2`, etc. dans le modèle de remplacement :

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Q : Que démontre l'exemple de code source pour la fonctionnalité « Reconnaître et remplacer les modèles de remplacement » dans Aspose.Words pour .NET ?

R : L'exemple de code source illustre l'utilisation de la fonctionnalité "Reconnaître et remplacer les modèles dans les modèles de remplacement" dans Aspose.Words pour .NET. Il montre comment créer un document, insérer du texte, effectuer une recherche et un remplacement de texte à l'aide d'expressions régulières et utiliser des groupes capturés dans le modèle de remplacement pour transformer dynamiquement le texte correspondant.

#### Q : Où puis-je trouver plus d'informations et d'exemples sur l'utilisation des expressions régulières dans Aspose.Words pour .NET ?

: Pour plus d'informations et d'exemples sur l'utilisation des expressions régulières dans Aspose.Words pour .NET, vous pouvez vous référer à la documentation officielle et au référentiel Aspose.Words GitHub. La documentation fournit des explications détaillées et des exemples de code pour divers scénarios impliquant des expressions régulières et la manipulation de texte dans Aspose.Words pour .NET.

#### Q : Puis-je manipuler d'autres aspects du document en fonction des groupes capturés lors de la recherche et du remplacement de texte ?

R : Oui, vous pouvez manipuler d'autres aspects du document en fonction des groupes capturés lors de la recherche et du remplacement de texte. En plus d'effectuer des substitutions de texte, vous pouvez modifier la mise en forme, les styles, la structure du document et d'autres éléments en fonction des groupes capturés à l'aide des différentes API fournies par Aspose.Words pour .NET.

#### Q : Existe-t-il des limitations ou des considérations lors de l'utilisation d'expressions régulières et de groupes capturés dans Aspose.Words pour .NET ?

R : Bien que les expressions régulières et les groupes capturés offrent de puissantes fonctionnalités de recherche et de remplacement de texte dans Aspose.Words pour .NET, il est important de prendre en compte la complexité et les implications en termes de performances. Des expressions régulières très complexes et un grand nombre de groupes capturés peuvent avoir un impact sur les performances. Il est recommandé de tester et d'optimiser les expressions régulières pour vos cas d'utilisation spécifiques afin d'assurer une manipulation efficace des documents.

#### Q : Puis-je utiliser la fonctionnalité "Reconnaître et remplacer les modèles de remplacement" avec des langues autres que l'anglais ?

R : Oui, la fonctionnalité "Reconnaître et remplacer les modèles de remplacement" dans Aspose.Words pour .NET peut être utilisée avec des langues autres que l'anglais. Les expressions régulières sont indépendantes de la langue et peuvent être conçues pour correspondre à des modèles spécifiques dans n'importe quelle langue. Vous pouvez ajuster le modèle d'expression régulière en fonction de la langue souhaitée et des modèles de texte spécifiques que vous souhaitez reconnaître et remplacer.