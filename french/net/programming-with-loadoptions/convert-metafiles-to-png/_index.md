---
title: Convertir les métafichiers en Png
linktitle: Convertir les métafichiers en Png
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des métafichiers en images PNG lors du téléchargement de documents avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-loadoptions/convert-metafiles-to-png/
---
Lorsque vous travaillez avec des documents dans une application C#, il peut être nécessaire de convertir des métafichiers en images PNG pour une meilleure compatibilité et un rendu précis. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement convertir des métafichiers en PNG lors du chargement d'un document. Dans ce guide étape par étape, nous vous expliquerons comment utiliser le code source Aspose.Words pour .NET C# pour charger un document en convertissant les métafichiers en PNG à l'aide des options de chargement LoadOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, y compris .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification de la mise en forme, l'ajout de sections et bien plus encore.

## Etape 1 : Définir le répertoire des documents

La première étape consiste à définir le répertoire où se trouvent vos documents. Vous devez spécifier le chemin d'accès complet au répertoire. Par exemple :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 2 : Configuration des options de chargement

Configurons maintenant les options de chargement de notre document. Utilisez la classe LoadOptions pour spécifier les paramètres de chargement. Par exemple :

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertMetafilesToPng = true };
```

Dans cet exemple, nous créons un nouvel objet LoadOptions et définissons la propriété ConvertMetafilesToPng sur true pour activer la conversion des métafichiers en PNG lors du chargement du document.

## Étape 3 : Chargement du document avec conversion des métafichiers en PNG

Maintenant que nous avons configuré les options de chargement, nous pouvons charger le document à l'aide de la classe Document et spécifier les options de chargement. Par exemple :

```csharp
Document doc = new Document(dataDir + "WMF with image.docx", loadOptions);
```

Dans cet exemple, nous chargeons le document "WMF avec image.docx" situé dans le répertoire des documents en utilisant les options de chargement spécifiées.

## Exemple de code source pour la fonctionnalité LoadOptions with Convert Metafiles To Png à l'aide de Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configurez les options de chargement avec la fonction "Convertir les métafichiers en Png"
LoadOptions loadOptions = new LoadOptions { ConvertMetafilesToPng = true };

// Charger le document avec les options spécifiées
Document doc = new Document(dataDir + "WMF with image.docx", loadOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment charger un document en convertissant des métafichiers en images PNG à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. La conversion des métafichiers en PNG assure une meilleure compatibilité et un rendu précis des documents.
