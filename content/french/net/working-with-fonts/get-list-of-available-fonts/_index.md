---
title: Obtenir la liste des polices disponibles
linktitle: Obtenir la liste des polices disponibles
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment obtenir une liste des polices disponibles à l'aide d'Aspose.Words pour .NET dans ce didacticiel détaillé étape par étape. Améliorez vos compétences en gestion des polices.
type: docs
weight: 10
url: /fr/net/working-with-fonts/get-list-of-available-fonts/
---
## Introduction

Vous avez déjà eu du mal à gérer les polices dans vos documents Word ? Si vous êtes un développeur .NET, Aspose.Words pour .NET est là pour vous sauver ! Cette puissante bibliothèque vous aide non seulement à créer et à manipuler des documents Word par programmation, mais offre également des fonctionnalités étendues de gestion des polices. Dans ce guide, nous vous guiderons pas à pas dans un didacticiel sur la façon d'obtenir une liste des polices disponibles à l'aide d'Aspose.Words pour .NET. Nous le décomposerons en étapes faciles à comprendre pour que vous puissiez suivre facilement. Alors, plongeons-nous dans le vif du sujet et faisons de la gestion des polices un jeu d'enfant !

## Prérequis

Avant de commencer, vous aurez besoin de quelques éléments :

-  Aspose.Words pour .NET : Assurez-vous que la bibliothèque Aspose.Words pour .NET est installée. Vous pouvez la télécharger à partir de[ici](https://releases.aspose.com/words/net/).
- Visual Studio : cet exemple utilise Visual Studio comme environnement de développement.
- .NET Framework : assurez-vous que .NET Framework est installé sur votre ordinateur.
- Répertoire de documents : un chemin de répertoire dans lequel vos documents sont stockés.

## Importer des espaces de noms

Tout d’abord, importez les espaces de noms nécessaires dans votre projet :

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

## Étape 1 : Initialiser les paramètres de police

La première étape consiste à initialiser les paramètres de police. Cela vous permettra de gérer les sources de polices de vos documents.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

- FontSettings : cette classe est utilisée pour spécifier les paramètres de substitution de police et les sources de police.
- fontSources : nous créons une liste de sources de polices existantes à partir des paramètres de police actuels.

## Étape 2 : Définir le répertoire des documents

Ensuite, spécifiez le chemin d'accès à votre répertoire de documents. C'est là qu'Aspose.Words recherchera les polices.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir : cette variable de chaîne contient le chemin d'accès au répertoire où se trouvent vos polices. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel.

## Étape 3 : Ajouter un dossier de polices personnalisées

Ajoutez maintenant une nouvelle source de dossier pour demander à Aspose.Words de rechercher des polices dans ce dossier.

```csharp
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
```

- FolderFontSource : cette classe représente une source de police de dossier. Le deuxième paramètre (`true`) indique s'il faut rechercher les polices de manière récursive dans les sous-dossiers.

## Étape 4 : mettre à jour les sources de polices

Ajoutez le dossier de polices personnalisées à la liste des sources de polices existantes et mettez à jour les paramètres de police.

```csharp
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

- fontSources.Add(folderFontSource) : ajoute le dossier de polices personnalisé aux sources de polices existantes.
- updatedFontSources : convertit la liste des sources de polices en un tableau.

## Étape 5 : Récupérer et afficher les polices

Enfin, récupérez les polices disponibles et affichez leurs détails.

```csharp
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
    Console.WriteLine("Version  : " + fontInfo.Version);
    Console.WriteLine("FilePath : " + fontInfo.FilePath);
}
```

- GetAvailableFonts() : récupère la liste des polices disponibles à partir de la première source de polices dans la liste mise à jour.
-  fontInfo : une instance de`PhysicalFontInfo` contenant des détails sur chaque police.

## Conclusion

Félicitations ! Vous avez récupéré avec succès une liste de polices disponibles à l'aide d'Aspose.Words pour .NET. Ce didacticiel vous a accompagné à chaque étape, de l'initialisation des paramètres de police à l'affichage des détails de police. Grâce à ces connaissances, vous pouvez désormais gérer facilement les polices dans vos documents Word. N'oubliez pas qu'Aspose.Words pour .NET est un outil puissant qui peut améliorer considérablement vos capacités de traitement de documents. Alors, allez-y et explorez d'autres fonctionnalités pour rendre votre processus de développement encore plus efficace.

## FAQ

### Puis-je utiliser Aspose.Words pour .NET avec d’autres frameworks .NET ?
Oui, Aspose.Words pour .NET est compatible avec divers frameworks .NET, notamment .NET Core et .NET 5+.

### Comment installer Aspose.Words pour .NET ?
Vous pouvez l'installer via NuGet Package Manager dans Visual Studio en recherchant « Aspose.Words ».

### Est-il possible d'ajouter plusieurs dossiers de polices personnalisés ?
 Oui, vous pouvez ajouter plusieurs dossiers de polices personnalisés en créant plusieurs`FolderFontSource` instances et les ajouter à la liste des sources de polices.

### Puis-je récupérer les détails d'une police à partir d'une source de police spécifique ?
 Oui, vous pouvez récupérer les détails de la police à partir de n'importe quelle source de police en spécifiant l'index de la source de police dans le`updatedFontSources` tableau.

### Aspose.Words pour .NET prend-il en charge la substitution de polices ?
Oui, il prend en charge la substitution de police pour garantir que le texte est rendu correctement même si la police d'origine n'est pas disponible.