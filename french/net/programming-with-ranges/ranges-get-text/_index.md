---
title: Plages Obtenir du texte
linktitle: Plages Obtenir du texte
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à extraire facilement du texte d'un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-ranges/ranges-get-text/
---

Aspose.Words pour .NET est une bibliothèque puissante pour créer, éditer et manipuler des documents Word dans une application C#. Parmi les fonctionnalités offertes par Aspose.Words figure la possibilité d'obtenir le texte contenu dans des plages spécifiques d'un document. Dans ce guide, nous vous expliquerons comment utiliser le code source C # de Aspose.Words pour .NET pour extraire du texte d'un document Word.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque populaire qui rend le travail avec les documents Word simple et efficace. Il offre un large éventail de fonctionnalités pour créer, éditer et manipuler des documents Word, y compris l'extraction de texte à partir de plages spécifiques.

## Chargement du document Word

La première étape consiste à charger le document Word dont vous souhaitez extraire le texte. Utilisez la classe Document pour charger le document à partir du fichier source. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Dans cet exemple, nous chargeons le document "Document.docx" situé dans le répertoire des documents.

## Extraction de texte d'une plage spécifique

Une fois le document chargé, vous pouvez accéder aux différentes plages du document et extraire le texte souhaité. Dans cet exemple, nous allons extraire tout le texte du document. Voici comment:

```csharp
string text = doc.Range.Text;
```

Dans cet exemple, nous utilisons la propriété Range de la classe Document pour accéder à la plage complète du document. Ensuite, nous utilisons la propriété Text pour obtenir le texte contenu dans cette plage.

## Affichage du texte extrait

Maintenant que nous avons extrait le texte de la plage spécifiée, nous pouvons l'afficher ou le traiter selon les besoins de votre application. Par exemple, vous pouvez l'afficher à l'écran ou l'enregistrer dans un fichier de sortie. Voici un exemple pour afficher le texte extrait :

```csharp
Console.WriteLine(text);
```

Dans cet exemple, nous utilisons la méthode WriteLine de la classe Console pour afficher le texte extrait dans la console.

### Exemple de code source pour la fonctionnalité "Obtenir du texte à partir de plages" avec Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Charger le document Word
Document doc = new Document(dataDir + "Document.docx");

// Extraire le texte du document
string text = doc.Range.Text;

// Afficher le texte extrait
Console.WriteLine(text);
```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser Aspose.Words pour .NET pour extraire du texte d'un document Word à l'aide du code source C# fourni. En suivant les étapes fournies, vous pouvez facilement extraire du texte de plages spécifiques dans vos documents Word dans votre application C#. Aspose.Words offre une flexibilité et une puissance considérables pour travailler avec le contenu du document, vous permettant de traiter et d'utiliser le texte en fonction de vos besoins spécifiques.