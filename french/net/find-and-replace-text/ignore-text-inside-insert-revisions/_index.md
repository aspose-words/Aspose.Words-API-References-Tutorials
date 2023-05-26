---
title: Ignorer le texte à l'intérieur des révisions d'insertion
linktitle: Ignorer le texte à l'intérieur des révisions d'insertion
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser la fonctionnalité "Ignorer le texte à l'intérieur des révisions d'insertion" d'Aspose.Words pour .NET pour manipuler les révisions d'insertion dans les documents Word.
type: docs
weight: 10
url: /fr/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Ignore Text Inside Insert Revisions dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité est utile lorsque nous voulons ignorer le texte à l'intérieur des révisions d'insertion lors de la manipulation de documents.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Création d'un nouveau document

 Avant de commencer à manipuler du texte dans les révisions d'insertion, nous devons créer un nouveau document en utilisant Aspose.Words pour .NET. Cela peut être fait en instanciant un`Document` objet:

```csharp
Document doc = new Document();
```

## Étape 2 : Insérer du texte avec suivi des révisions

 Une fois que nous avons un document, nous pouvons insérer du texte avec suivi des révisions à l'aide d'un`DocumentBuilder` objet. Par exemple, pour insérer le texte "Inséré" avec suivi des révisions, nous pouvons utiliser le`StartTrackRevisions`, `Writeln` et`StopTrackRevisions` méthodes :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Étape 3 : Insérer du texte non révisé

 En plus du texte avec suivi des révisions, nous pouvons également insérer du texte non révisé à l'aide de la`DocumentBuilder`objet. Par exemple, pour insérer le texte "Texte" sans révision, nous pouvons utiliser le`Write` méthode:

```csharp
builder.Write("Text");
```

## Étape 4 : Utilisation de la fonction Ignorer le texte à l'intérieur de l'insertion des révisions

 Pour ignorer le texte à l'intérieur des révisions d'insertion lors des opérations suivantes, nous pouvons utiliser un`FindReplaceOptions` objet et définissez le`IgnoreInserted` propriété à`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Étape 5 : Utiliser des expressions régulières pour rechercher et remplacer

Pour effectuer des opérations de recherche et de remplacement sur le texte du document, nous utiliserons des expressions régulières. Dans notre exemple, nous allons rechercher toutes les occurrences de la lettre "e" et les remplacer par un astérisque "* ". Nous utiliserons .NET`Regex` classe pour ça :

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Étape 6 : Affichage de la sortie du document modifié

Après avoir appliqué la recherche et le remplacement, nous pouvons afficher le contenu modifié du document à l'aide de la`GetText` méthode:

```csharp
Console.WriteLine(doc.GetText());
```

## Étape 7 : Modification des options pour inclure les révisions d'insertion

 Si nous voulons inclure le texte à l'intérieur des révisions d'insertion dans le résultat de sortie, nous pouvons modifier les options pour ne pas ignorer les révisions d'insertion. Pour cela nous fixerons le`IgnoreInserted` propriété à`false`:

```csharp
options.IgnoreInserted = false;
```

## Étape 8 : Affichage du document modifié avec insertion des révisions

Après avoir modifié les options, nous pouvons effectuer à nouveau la recherche et le remplacement pour obtenir le résultat avec le texte à l'intérieur des révisions d'insertion incluses :

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Exemple de code source pour Ignorer le texte à l'intérieur des révisions d'insertion à l'aide de Aspose.Words pour .NET

Voici l'exemple de code source complet pour démontrer l'utilisation de la fonction Ignore Text Inside Insert Revisions avec Aspose.Words pour .NET :


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Insérer du texte avec suivi des révisions.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Insérer du texte non révisé.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Ignore Text Inside Insert Revisions dans Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour créer un document, insérer du texte avec suivi des révisions et du texte non révisé, utiliser la fonction Ignorer le texte à l'intérieur de l'insertion des révisions, effectuer des opérations de recherche et de remplacement avec des expressions régulières et afficher le document modifié.