---
title: Utiliser le dossier temporaire
linktitle: Utiliser le dossier temporaire
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser un dossier temporaire lors du téléchargement de documents avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-loadoptions/use-temp-folder/
---

Lorsque vous travaillez avec des documents Word dans une application C#, il peut être nécessaire d'utiliser un dossier temporaire pour stocker les fichiers temporaires générés lors du traitement du document. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement spécifier un dossier temporaire à l'aide des options de chargement LoadOptions. Dans ce guide étape par étape, nous allons vous montrer comment utiliser le code source Aspose.Words pour .NET C# pour charger un document à l'aide d'un dossier temporaire spécifié à l'aide des options de chargement LoadOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, y compris .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification de la mise en forme, l'ajout de sections et bien plus encore.

## Configuration des options de chargement

La première étape consiste à configurer les options de chargement de notre document. Utilisez la classe LoadOptions pour spécifier les paramètres de chargement. Dans notre cas, nous devons définir la propriété TempFolder sur le chemin du dossier temporaire souhaité. Voici comment procéder :

```csharp
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };
```

Nous créons un nouvel objet LoadOptions et définissons la propriété TempFolder sur le chemin du dossier temporaire souhaité.

## Télécharger le document à l'aide du dossier temporaire spécifié

Maintenant que nous avons configuré les options de chargement, nous pouvons charger le document à l'aide de la classe Document et spécifier les options de chargement. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

Dans cet exemple, nous chargeons le document "Document.docx" situé dans le répertoire des documents en utilisant les options de chargement spécifiées.

### Exemple de code source pour LoadOptions avec la fonctionnalité "Utiliser le dossier temporaire" en utilisant Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configurez les options de chargement avec la fonction "Utiliser le dossier temporaire"
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };

// Charger le document à l'aide d'un dossier temporaire spécifié
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment télécharger un document à l'aide d'un dossier temporaire spécifié à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. L'utilisation d'un dossier temporaire permet aux fichiers temporaires générés lors du traitement du document d'être stockés de manière organisée et efficace.
