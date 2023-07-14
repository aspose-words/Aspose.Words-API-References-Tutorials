---
title: Chm de charge
linktitle: Chm de charge
second_title: API de traitement de documents Aspose.Words
description: Apprenez à charger des fichiers CHM avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-loadoptions/load-chm/
---

Lorsque Words Processing with HTML Help (CHM) fichiers dans une application C#, il est important de pouvoir les charger correctement. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement charger des fichiers CHM en utilisant les options de chargement appropriées. Dans ce guide étape par étape, nous allons vous montrer comment utiliser le code source Aspose.Words pour .NET C# pour charger un fichier CHM à l'aide des options de chargement LoadOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, y compris .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification de la mise en forme, l'ajout de sections et bien plus encore.

## Configuration des options de chargement

La première étape consiste à configurer les options de chargement de notre fichier CHM. Utilisez la classe LoadOptions pour spécifier les paramètres de chargement. Dans notre cas, nous devons définir la propriété Encoding sur l'encodage approprié pour les fichiers CHM, généralement "windows-1251". Voici comment procéder :

```csharp
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };
```

Nous créons un nouvel objet LoadOptions et définissons la propriété Encoding sur l'encodage "windows-1251" pour les fichiers CHM.

## Chargement du fichier CHM

Maintenant que nous avons configuré les options de chargement, nous pouvons charger le fichier CHM à l'aide de la classe Document et spécifier les options de chargement. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

Dans cet exemple, nous chargeons le fichier CHM "HTML help.chm" situé dans le répertoire des documents en utilisant les options de chargement spécifiées.

### Exemple de code source pour LoadOptions avec la fonctionnalité "Load Chm" utilisant Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configuration des options de chargement avec la fonctionnalité "Load Chm"
LoadOptions loadOptions = new LoadOptions { Encoding = Encoding. GetEncoding("windows-1251") };

// Charger le fichier CHM avec les options spécifiées
Document doc = new Document(dataDir + "HTML help.chm", loadOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment charger un fichier CHM à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. Le chargement correct des fichiers CHM est essentiel pour pouvoir les manipuler et les convertir efficacement avec Aspose.Words.