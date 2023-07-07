---
title: Granularité de la comparaison
linktitle: Granularité de la comparaison
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à comparer la fonctionnalité de granularité d'Aspose.Words pour .NET qui permet de comparer les documents caractère par caractère, en signalant les modifications apportées.
type: docs
weight: 10
url: /fr/net/compare-documents/comparison-granularity/
---
Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la fonction Compare Granularity d'Aspose.Words pour .NET.

## Étape 1 : Présentation

La fonction Compare Granularity d'Aspose.Words pour .NET vous permet de comparer des documents au niveau des caractères. Cela signifie que chaque caractère sera comparé et que les modifications seront signalées en conséquence.

## Étape 2 : Configurer l'environnement

Avant de commencer, vous devez configurer votre environnement de développement pour qu'il fonctionne avec Aspose.Words pour .NET. Assurez-vous que la bibliothèque Aspose.Words est installée et que vous disposez d'un projet C# approprié pour intégrer le code.

## Étape 3 : Ajouter les assemblages requis

Pour utiliser la fonction Compare Granularity de Aspose.Words pour .NET, vous devez ajouter les assemblys nécessaires à votre projet. Assurez-vous d'avoir les bonnes références à Aspose.Words dans votre projet.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Étape 4 : Création de documents

Dans cette étape, nous allons créer deux documents à l'aide de la classe DocumentBuilder. Ces documents seront utilisés pour la comparaison.

```csharp
// Créer le document A.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Créer le document B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Étape 5 : Configuration des options de comparaison

Dans cette étape, nous allons configurer les options de comparaison pour spécifier la granularité de la comparaison. Ici, nous utiliserons la granularité au niveau des caractères.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Étape 6 : Comparaison de documents

Comparons maintenant les documents à l'aide de la méthode Compare de la classe Document. Les modifications seront enregistrées dans le document A.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 Le`Compare`La méthode compare le document A au document B et enregistre les modifications apportées au document A. Vous pouvez spécifier le nom de l'auteur et la date de comparaison pour référence.

## Conclusion

Dans cet article, nous avons exploré la fonction Compare Granularity d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de comparer des documents au niveau du personnage et de signaler les modifications. Vous pouvez utiliser ces connaissances pour effectuer des comparaisons détaillées de documents dans vos projets.

### Exemple de code source pour la granularité de comparaison à l'aide d'Aspose.Words pour .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```
