---
title: Changer le style du niveau de toc
linktitle: Changer le style du niveau de toc
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à modifier facilement le style d'un niveau de table des matières dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-of-content/change-style-of-toc-level/
---

Aspose.Words pour .NET est une bibliothèque puissante pour créer, éditer et manipuler des documents Word dans une application C#. Parmi les fonctionnalités offertes par Aspose.Words, il y a la possibilité de changer le style d'un niveau spécifique de la table des matières d'un document. Dans ce guide, nous allons vous montrer comment utiliser le code source C# d'Aspose.Words pour .NET pour changer le style d'un niveau de la table des matières d'un document Word.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque populaire qui rend le travail avec les documents Word simple et efficace. Il offre un large éventail de fonctionnalités pour créer, éditer et manipuler des documents Word, y compris la modification du style de la table des matières.

## Création d'un nouveau document

La première étape consiste à créer un nouveau document Word dans lequel vous souhaitez modifier le style de la table des matières. Utilisez la classe Document pour créer un nouveau document. Voici un exemple :

```csharp
Document doc = new Document();
```

Dans cet exemple, nous créons un nouveau document vide.

## Changer le style d'un niveau de table des matières

Une fois le document créé, vous pouvez accéder aux styles de document et modifier le style utilisé pour un niveau spécifique de la table des matières. Dans cet exemple, nous allons modifier le style utilisé pour le premier niveau de la table des matières. Voici comment:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

Dans cet exemple, nous utilisons la propriété Styles de la classe Document pour accéder aux styles de document. Ensuite, nous utilisons l'identifiant de style StyleIdentifier.Toc1 pour accéder au style utilisé pour le premier niveau de la table des matières. Enfin, nous modifions la propriété Font.Bold du style pour le rendre gras.

## Enregistrer le document modifié

Une fois que vous avez apporté les modifications nécessaires au style de la table des matières, vous pouvez enregistrer le document modifié à l'aide de la méthode Save de la classe Document. Voici un exemple :

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

Dans cet exemple, nous enregistrons le document modifié sous "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx".

## Exemple de code source pour la fonctionnalité "Modifier le style d'un niveau de table des matières" avec Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer un nouveau document
Document doc = new Document();

// Modification du style du premier niveau de la table des matières
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;

// Enregistrer le document modifié
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser Aspose.Words pour .NET pour modifier le style d'un niveau de la table des matières d'un document Word à l'aide du code source C# fourni. En suivant les étapes fournies, vous pouvez facilement personnaliser le style de la table des matières de vos documents Word dans votre application C#. Aspose.Words offre une flexibilité et une puissance considérables pour travailler avec les styles et la mise en forme de vos documents, vous permettant de créer des documents Word attrayants et professionnels.