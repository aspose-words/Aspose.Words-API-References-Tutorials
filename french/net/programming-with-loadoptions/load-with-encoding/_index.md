---
title: Charger avec encodage
linktitle: Charger avec encodage
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à charger un document avec un encodage spécifié à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-loadoptions/load-with-encoding/
---
Lorsque vous travaillez avec des documents texte dans une application C#, il est important de pouvoir les charger correctement en spécifiant le codage correct. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement charger des documents texte avec l'encodage souhaité à l'aide des options de chargement LoadOptions. Dans ce guide étape par étape, nous vous expliquerons comment utiliser le code source Aspose.Words pour .NET C# pour charger un document texte avec l'encodage spécifié à l'aide des options de chargement LoadOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, y compris .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification de la mise en forme, l'ajout de sections et bien plus encore.

## Configuration des options de chargement

La première étape consiste à configurer les options de chargement de notre document texte. Utilisez la classe LoadOptions pour spécifier les paramètres de chargement. Dans notre cas, nous devons définir la propriété Encoding sur l'encodage souhaité, par exemple, Encoding.UTF7 pour l'encodage UTF-7. Voici comment procéder :

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding.UTF7 };
```

Nous créons un nouvel objet LoadOptions et définissons la propriété Encoding sur Encoding.UTF7 pour spécifier le codage UTF-7.

## Chargement du document avec l'encodage spécifié

Maintenant que nous avons configuré les options de chargement, nous pouvons charger le document à l'aide de la classe Document et spécifier les options de chargement. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Encoded in UTF-7.txt", loadOptions);
```

Dans cet exemple, nous chargeons le document "Encodé en UTF-7.txt" situé dans le répertoire des documents en utilisant les options de chargement spécifiées.

### Exemple de code source pour LoadOptions avec la fonctionnalité "Load With Encoding" à l'aide d'Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configurez les options de chargement avec l'encodage souhaité (UTF-7)
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding.UTF7 };

// Charger le document avec l'encodage spécifié
Document doc = new Document(dataDir + "Encoded in UTF-7.txt", loadOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment charger un document texte avec un encodage spécifié à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. Le chargement de documents texte avec le codage approprié garantit une lecture correcte et précise du contenu de votre application.