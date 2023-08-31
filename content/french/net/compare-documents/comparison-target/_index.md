---
title: Cible de comparaison dans un document Word
linktitle: Cible de comparaison dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à comparer la cible dans la fonction de document Word d'Aspose.Words pour .NET qui vous permet de comparer des documents et de générer un nouveau document contenant les modifications apportées.
type: docs
weight: 10
url: /fr/net/compare-documents/comparison-target/
---
Voici un guide étape par étape pour expliquer le code source C# ci-dessous, qui utilise la cible de comparaison dans la fonctionnalité de document Word d'Aspose.Words pour .NET.

## Étape 1 : Présentation

La fonction de comparaison cible d'Aspose.Words pour .NET vous permet de comparer deux documents et de générer un nouveau document contenant les modifications apportées au document cible. Cela peut être utile pour suivre les modifications apportées entre différentes versions d'un document.

## Étape 2 : Configurer l'environnement

Avant de commencer, vous devez configurer votre environnement de développement pour qu'il fonctionne avec Aspose.Words pour .NET. Assurez-vous que la bibliothèque Aspose.Words est installée et que vous disposez d'un projet C# approprié pour intégrer le code.

## Étape 3 : Ajouter les assemblages requis

Pour utiliser la fonctionnalité cible de comparaison d'Aspose.Words pour .NET, vous devez ajouter les assemblys nécessaires à votre projet. Assurez-vous d'avoir les bonnes références à Aspose.Words dans votre projet.

```csharp
using Aspose.Words;
```

## Étape 4 : Initialisation du document

Dans cette étape, nous allons initialiser deux documents pour comparaison. Vous devez spécifier le chemin du répertoire où se trouvent vos documents, ainsi que le nom du document source.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Initialisation du document A à comparer.
Document docA = new Document(dataDir + "DocumentA.docx");

// Clonez le document A pour créer une copie identique du document B.
Document docB = docA.Clone();
```

## Étape 5 : Configuration des options de comparaison

Dans cette étape, nous allons configurer les options de comparaison pour spécifier le comportement de la comparaison. Les options incluent la possibilité d'ignorer la mise en forme, ainsi que la cible de comparaison, qui est l'option "Afficher les modifications dans" dans la boîte de dialogue "Comparer les documents" de Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Étape 6 : Comparaison de documents

Nous allons maintenant comparer les documents et générer le résultat dans un nouveau document.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 Le`Compare`La méthode compare le document A au document B et enregistre les modifications apportées au document A. Vous pouvez spécifier le nom d'utilisateur et la date de comparaison pour référence.

### Exemple de code source pour la cible de comparaison à l'aide d'Aspose.Words pour .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Se rapporte à l'option "Afficher les modifications dans" de Microsoft Word dans la boîte de dialogue "Comparer les documents".
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Conclusion

Dans cet article, nous avons exploré la fonctionnalité de cible diff d'Aspose.Words pour .NET. Cette fonctionnalité permet de comparer deux documents et de générer un nouveau document contenant les modifications apportées. Vous pouvez utiliser ces connaissances pour suivre les modifications entre les différentes versions de vos documents.

### FAQ

#### Q : Quel est le but de l'utilisation de la cible de comparaison dans Aspose.Words pour .NET ?

R : La cible de comparaison dans Aspose.Words pour .NET vous permet de comparer deux documents et de générer un nouveau document contenant les modifications apportées au document cible. Cette fonctionnalité est utile pour suivre les modifications apportées entre différentes versions d'un document et visualiser les différences dans un document distinct.

#### Q : Comment utiliser la cible de comparaison dans Aspose.Words pour .NET ?

R : Pour utiliser la cible de comparaison dans Aspose.Words pour .NET, suivez ces étapes :
1. Configurez votre environnement de développement avec la bibliothèque Aspose.Words.
2. Ajoutez les assemblys nécessaires à votre projet en faisant référence à Aspose.Words.
3.  Initialisez les documents que vous souhaitez comparer à l'aide de la`Document` classe ou la`DocumentBuilder` classe.
4.  Configurez les options de comparaison en créant un`CompareOptions` objet et propriétés de définition telles que`IgnoreFormatting` et`Target` (par exemple,`ComparisonTargetType.New` pour cible de comparaison).
5.  Utilisez le`Compare` méthode sur un document, en passant l'autre document et le`CompareOptions` objet en tant que paramètres. Cette méthode comparera les documents et enregistrera les modifications dans le premier document.

####  Q : Quel est le but du`Target` property in the `CompareOptions` class?

 R : Le`Target` propriété dans le`CompareOptions` La classe vous permet de spécifier la cible de comparaison, qui est similaire à l'option "Afficher les modifications dans" de la boîte de dialogue "Comparer les documents" de Microsoft Word. L'objectif peut être fixé à`ComparisonTargetType.New` pour afficher les modifications dans un nouveau document,`ComparisonTargetType.Current` pour afficher les modifications dans le document actuel, ou`ComparisonTargetType.Formatting` pour afficher uniquement les changements de mise en forme.