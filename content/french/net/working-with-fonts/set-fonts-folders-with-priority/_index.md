---
title: Définir les dossiers de polices avec priorité
linktitle: Définir les dossiers de polices avec priorité
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir la priorité des dossiers de polices dans les documents Word à l'aide d'Aspose.Words pour .NET. Notre guide garantit que vos documents s'affichent parfaitement à chaque fois.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folders-with-priority/
---
## Introduction

Dans le monde de la manipulation de documents, la définition de dossiers de polices personnalisés peut faire toute la différence en garantissant un rendu parfait de vos documents, quel que soit l'endroit où ils sont visualisés. Aujourd'hui, nous allons découvrir comment définir les dossiers de polices en priorité dans vos documents Word à l'aide d'Aspose.Words pour .NET. Ce guide complet vous guidera à travers chaque étape, rendant le processus aussi fluide que possible.

## Conditions préalables

Avant de commencer, assurons-nous que nous avons tout ce dont nous avons besoin. Voici une liste de contrôle rapide :

-  Aspose.Words pour .NET : vous devez installer cette bibliothèque. Si vous ne l'avez pas encore, vous pouvez[téléchargez-le ici](https://releases.aspose.com/words/net/).
- Environnement de développement : assurez-vous de disposer d'un environnement de développement .NET fonctionnel, comme Visual Studio.
-  Répertoire de documents : assurez-vous de disposer d'un répertoire pour vos documents. Pour nos exemples, nous utiliserons`"YOUR DOCUMENT DIRECTORY"` comme espace réservé pour ce chemin.

## Importer des espaces de noms

Tout d’abord, nous devons importer les espaces de noms nécessaires. Ces espaces de noms sont essentiels pour accéder aux classes et méthodes fournies par Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Maintenant, décomposons chaque étape pour définir les dossiers de polices en priorité.

## Étape 1 : Configurez vos sources de polices

Pour commencer, vous souhaiterez définir les sources de polices. C'est ici que vous indiquez à Aspose.Words où rechercher les polices. Vous pouvez spécifier plusieurs dossiers de polices et même définir leur priorité.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
    new SystemFontSource(), 
    new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

Dans cet exemple, nous définissons deux sources de polices :
- SystemFontSource : il s'agit de la source de polices par défaut qui inclut toutes les polices installées sur votre système.
-  FolderFontSource : il s'agit d'un dossier de polices personnalisées situé dans`C:\\MyFonts\\` . Le`true` Le paramètre spécifie que ce dossier doit être analysé de manière récursive, et`1` fixe sa priorité.

## Étape 2 : Chargez votre document

Ensuite, chargez le document avec lequel vous souhaitez travailler. Assurez-vous que le document se trouve dans le répertoire spécifié.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Cette ligne de code charge un document nommé`Rendering.docx` à partir de votre répertoire de documents.

## Étape 3 : Enregistrez votre document avec les nouveaux paramètres de police

Enfin, enregistrez votre document. Lorsque vous enregistrez le document, Aspose.Words utilisera les paramètres de police que vous avez spécifiés.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

 Cela enregistre le document au format PDF dans votre répertoire de documents sous le nom`WorkingWithFonts.SetFontsFoldersWithPriority.pdf`.

## Conclusion

Et voilà ! Vous avez configuré avec succès les dossiers de polices avec priorité à l'aide d'Aspose.Words pour .NET. En spécifiant des dossiers et des priorités de polices personnalisés, vous pouvez garantir que vos documents s'affichent de manière cohérente, quel que soit l'endroit où ils sont affichés. Ceci est particulièrement utile dans les environnements dans lesquels des polices spécifiques ne sont pas installées par défaut.

## FAQ

### Pourquoi devrais-je définir des dossiers de polices personnalisés ?
La définition de dossiers de polices personnalisés garantit que vos documents s'affichent correctement, même s'ils utilisent des polices non installées sur le système sur lequel ils sont affichés.

### Puis-je définir plusieurs dossiers de polices personnalisées ?
Oui, vous pouvez spécifier plusieurs dossiers de polices. Aspose.Words vous permet de définir la priorité de chaque dossier, en garantissant que les polices les plus importantes soient trouvées en premier.

### Que se passe-t-il si une police est absente de toutes les sources spécifiées ?
Si une police est manquante dans toutes les sources spécifiées, Aspose.Words utilisera une police de secours pour garantir que le document est toujours lisible.

### Puis-je modifier la priorité des polices système ?
Les polices système sont toujours incluses par défaut, mais vous pouvez définir leur priorité par rapport à vos dossiers de polices personnalisées.

### Est-il possible d'utiliser des chemins réseau pour les dossiers de polices personnalisées ?
Oui, vous pouvez spécifier des chemins réseau en tant que dossiers de polices personnalisés, ce qui vous permet de centraliser les ressources de polices sur un emplacement réseau.