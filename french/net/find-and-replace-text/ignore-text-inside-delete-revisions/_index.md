---
title: Ignorer le texte à l'intérieur Supprimer les révisions
linktitle: Ignorer le texte à l'intérieur Supprimer les révisions
second_title: API de traitement de documents Aspose.Words
description: Apprenez à utiliser la fonctionnalité "Ignorer le texte à l'intérieur de supprimer les révisions" d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonctionnalité "Ignorer le texte à l'intérieur de supprimer les révisions" dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité est utile lorsque nous voulons ignorer le texte à l'intérieur des révisions de suppression lors du traitement de mots avec des documents.

## Présentation de la bibliothèque Aspose.Words pour .NET

Avant de plonger dans les détails du code, permettez-moi de présenter brièvement la bibliothèque Aspose.Words pour .NET. C'est une bibliothèque puissante qui permet de créer, modifier et convertir des documents Word dans des applications .NET. Il offre de nombreuses fonctionnalités avancées pour le traitement de texte avec des documents, dont la gestion des révisions.

## Comprendre la fonctionnalité "Ignorer le texte à l'intérieur de supprimer les révisions"

La fonctionnalité "Ignorer le texte à l'intérieur des révisions de suppression" dans Aspose.Words pour .NET vous permet de spécifier si le texte à l'intérieur des révisions de suppression doit être ignoré lors de certaines opérations, telles que la recherche et le remplacement de texte. Lorsque cette fonctionnalité est activée, le texte supprimé dans les révisions n'est pas pris en compte lors des opérations.

## Étape 1 : Création d'un nouveau document à l'aide d'Aspose.Words pour .NET

 Avant de commencer à manipuler du texte dans un document, nous devons créer un nouveau document en utilisant Aspose.Words pour .NET. Cela peut être fait en instanciant un`Document` objet:

```csharp
Document doc = new Document();
```

## Étape 2 : Insertion de texte non révisé dans le document

 Une fois que nous avons un document, nous pouvons insérer du texte non révisé à l'aide d'un`DocumentBuilder` objet. Par exemple, pour insérer le texte "Texte supprimé", nous pouvons utiliser le`Writeln` et`Write` méthodes :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Étape 3 : Suppression d'un paragraphe avec suivi des révisions

Pour illustrer l'utilisation de la fonctionnalité "Ignorer le texte à l'intérieur de supprimer les révisions", nous supprimerons un paragraphe du document à l'aide du suivi des révisions. Cela nous permettra de voir comment cette fonctionnalité affecte les opérations ultérieures.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Étape 4 : Application de la fonctionnalité "Ignorer le texte à l'intérieur de supprimer les révisions"

 Maintenant que nous avons préparé notre document en supprimant un paragraphe, nous pouvons activer la fonctionnalité "Ignorer le texte à l'intérieur de supprimer les révisions" à l'aide d'un`FindReplaceOptions` objet. Nous fixerons le`IgnoreDeleted` propriété à`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Étape 5 : Utiliser des expressions régulières pour rechercher et remplacer

Pour effectuer des opérations de recherche et de remplacement sur le texte du document, nous utiliserons des expressions régulières. Dans notre exemple, nous allons rechercher toutes les occurrences de la lettre "e" et les remplacer par un astérisque "* ". .FILET`Regex` la classe est utilisée pour cela:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Étape 6 : Affichage de la sortie du document modifié

Après avoir appliqué la recherche et le remplacement, nous pouvons afficher le contenu modifié du document à l'aide de la`GetText` méthode:

```csharp
Console.WriteLine(doc.GetText());
```

## Étape 7 : Modification des options pour inclure le texte supprimé

 Si nous voulons inclure du texte supprimé dans le résultat de sortie, nous pouvons modifier les options pour ne pas ignorer le texte supprimé. Pour cela nous fixerons le`IgnoreDeleted` propriété à`false`:

```csharp
options. IgnoreDeleted = false;
```

## Étape 8 : Sortie du document modifié avec le texte supprimé

Après avoir modifié les options, nous pouvons effectuer à nouveau la recherche et le remplacement pour obtenir le résultat avec le texte supprimé inclus :

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Exemple de code source pour Ignorer le texte à l'intérieur de supprimer les révisions à l'aide de Aspose.Words pour .NET

Voici l'exemple de code source complet pour illustrer l'utilisation de la fonctionnalité "Ignorer le texte à l'intérieur de supprimer les révisions" avec Aspose.Words pour .NET :

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Insérer du texte non révisé.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Supprimer le premier paragraphe avec suivi des révisions.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonctionnalité "Ignorer le texte à l'intérieur de supprimer les révisions" dans Aspose.Words pour .NET. Cette fonctionnalité est utile pour ignorer le texte à l'intérieur des révisions de suppression lors de la manipulation de documents. Nous avons suivi un guide étape par étape pour créer un document, insérer du texte, supprimer un paragraphe avec suivi des révisions, appliquer la fonctionnalité "Ignorer le texte à l'intérieur de supprimer les révisions" et effectuer des opérations de recherche et de remplacement.

### FAQ

#### Q : Qu'est-ce que la fonction "Ignorer le texte à l'intérieur de supprimer les révisions" dans Aspose.Words pour .NET ?

R : La fonction "Ignorer le texte à l'intérieur des révisions de suppression" dans Aspose.Words pour .NET vous permet de spécifier si le texte à l'intérieur des révisions de suppression doit être ignoré lors de certaines opérations, telles que la recherche et le remplacement de texte. Lorsque cette fonctionnalité est activée, le texte supprimé dans les révisions n'est pas pris en compte lors des opérations.

#### Q : Qu'est-ce qu'Aspose.Words pour .NET ?

: Aspose.Words pour .NET est une bibliothèque puissante pour créer, éditer et convertir des documents Word en applications .NET. Il offre de nombreuses fonctionnalités avancées pour le traitement de texte avec des documents, dont la gestion des révisions.

#### Q : Comment créer un nouveau document dans Aspose.Words pour .NET ?

 R : Avant de commencer à manipuler du texte dans un document, vous devez créer un nouveau document à l'aide de Aspose.Words pour .NET. Cela peut être fait en instanciant un`Document` objet. Voici un exemple de code pour créer un nouveau document :

```csharp
Document doc = new Document();
```

#### Q : Comment insérer du texte non édité dans un document à l'aide d'Aspose.Words pour .NET ?

 R : Une fois que vous avez un document, vous pouvez insérer du texte non révisé à l'aide d'un`DocumentBuilder` objet. Par exemple, pour insérer le texte "Texte supprimé", vous pouvez utiliser le`Writeln` et`Write` méthodes :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### Q : Comment supprimer un paragraphe avec suivi des révisions dans Aspose.Words pour .NET ?

R : Pour illustrer l'utilisation de la fonction "Ignorer le texte à l'intérieur de la suppression des révisions", nous supprimerons un paragraphe du document à l'aide du suivi des révisions. Cela nous permettra de voir comment cette fonction affecte les opérations ultérieures.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### Q : Comment activer la fonctionnalité "Ignorer le texte à l'intérieur de supprimer les révisions" dans Aspose.Words pour .NET ?

 R : Maintenant que nous avons préparé notre document en supprimant un paragraphe, nous pouvons activer la fonctionnalité "Ignorer le texte à l'intérieur de supprimer les révisions" à l'aide d'un`FindReplaceOptions` objet. Nous fixerons le`IgnoreDeleted` propriété à`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### Q : Comment rechercher et remplacer à l'aide d'expressions régulières dans Aspose.Words pour .NET ?

R : Pour effectuer des opérations de recherche et de remplacement sur le texte du document, nous utiliserons des expressions régulières. Dans notre exemple, nous allons rechercher toutes les occurrences de la lettre "e" et les remplacer par un astérisque "* ". Nous utiliserons le .NET`Regex` classe pour ça :

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Q : Comment afficher le contenu du document modifié dans Aspose.Words pour .NET ?

R : Après avoir appliqué la recherche et le remplacement, nous pouvons afficher le contenu modifié du document à l'aide de la`GetText` méthode:

```csharp
Console.WriteLine(doc.GetText());
```

#### Q : Comment inclure du texte supprimé dans le résultat de sortie dans Aspose.Words pour .NET ?

 R : Si nous voulons inclure du texte supprimé dans le résultat de sortie, nous pouvons modifier les options pour ne pas ignorer le texte supprimé. Pour cela, nous fixerons le`IgnoreDeleted` propriété à`false`:

```csharp
options. IgnoreDeleted = false;
```

#### Q : Comment afficher un document modifié avec du texte supprimé dans Aspose.Words pour .NET ?

R : Après avoir modifié les options, nous pouvons effectuer une nouvelle recherche et remplacer pour obtenir le résultat avec le texte supprimé inclus :

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
