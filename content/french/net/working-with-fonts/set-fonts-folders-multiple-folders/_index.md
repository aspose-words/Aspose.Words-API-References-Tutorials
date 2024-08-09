---
title: Définir des dossiers de polices Plusieurs dossiers
linktitle: Définir des dossiers de polices Plusieurs dossiers
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir plusieurs dossiers de polices dans vos documents Word à l'aide d'Aspose.Words pour .NET. Ce guide étape par étape garantit que vos documents utilisent exactement les polices dont vous avez besoin.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-fonts-folders-multiple-folders/
---
## Introduction

Vous êtes-vous déjà demandé comment gérer plusieurs sources de polices dans vos documents Word ? Peut-être avez-vous une collection de polices dispersées dans différents dossiers et vous avez besoin d'un moyen de garantir que vos documents les utilisent de manière transparente. Eh bien, vous avez de la chance ! Aujourd'hui, nous examinons comment définir des dossiers de polices à l'aide d'Aspose.Words pour .NET. Ce guide vous guidera étape par étape tout au long du processus, garantissant que vos documents auront exactement l'apparence que vous souhaitez.

## Conditions préalables

Avant de commencer, assurons-nous que vous disposez de tout ce dont vous avez besoin. Voici ce que vous devrez suivre :

-  Aspose.Words pour .NET : si vous ne l'avez pas déjà fait, téléchargez et installez Aspose.Words pour .NET. Vous pouvez l'obtenir[ici](https://releases.aspose.com/words/net/).
- Environnement de développement : Visual Studio ou tout autre environnement de développement compatible .NET.
- Connaissance de base de C# : Une petite familiarité avec C# vous aidera à suivre les exemples.
- Fichiers de polices : assurez-vous que vos fichiers de polices sont stockés dans des répertoires auxquels vous pouvez facilement accéder.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires dans votre projet C#. Cela garantit que vous avez accès à toutes les fonctionnalités Aspose.Words dont vous aurez besoin.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Avec cet ensemble, plongeons dans le guide étape par étape pour définir les dossiers de polices dans Aspose.Words pour .NET.

## Étape 1 : Chargez votre document

Très bien, commençons par charger le document Word avec lequel vous souhaitez travailler. Assurez-vous que le chemin du document est prêt. Pour cet exemple, nous utiliserons un document nommé « Rendering.docx ».

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Ici, nous chargeons le document à partir du répertoire spécifié. Assez simple, non ?

## Étape 2 : créer un objet FontSettings

 Ensuite, nous devons créer un`FontSettings` objet. Cet objet nous permettra de gérer les sources de polices de notre document.

```csharp
FontSettings fontSettings = new FontSettings();
```

 Ce`FontSettings`L'objet nous aidera à définir les dossiers de polices à utiliser.

## Étape 3 : définir les dossiers de polices

Vient maintenant la partie cruciale : la configuration des dossiers de polices. C'est ici que vous spécifiez les répertoires où se trouvent vos polices. Dans cet exemple, nous avons des polices dans "C:\MyFonts\" et " D:\Divers\Fonts\".

```csharp
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

Le deuxième paramètre (`true` ) indique que ces dossiers remplaceront toutes les sources de polices par défaut. Si vous souhaitez également conserver les sources de polices système, vous pouvez utiliser une combinaison de`GetFontSources`et`SetFontSources`.

## Étape 4 : appliquer les paramètres de police au document

Une fois les dossiers de polices définis, nous devons appliquer ces paramètres à notre document. Cela garantit que le document utilise les polices spécifiées lors du rendu.

```csharp
doc.FontSettings = fontSettings;
```

## Étape 5 : Enregistrez le document

Enfin, sauvons le document. Nous l'enregistrerons au format PDF pour voir les polices en action.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

Et voilà ! Vous avez correctement défini plusieurs dossiers de polices pour votre document.

## Conclusion

La gestion des polices dans vos documents peut sembler une tâche ardue, mais avec Aspose.Words for .NET, c'est un jeu d'enfant ! En suivant ces étapes simples, vous pouvez garantir à vos documents un aspect professionnel et utiliser les polices exactes dont vous avez besoin. Que vous travailliez sur un projet nécessitant une image de marque spécifique ou que vous souhaitiez simplement plus de contrôle sur l'apparence de votre document, la définition des dossiers de polices est une compétence qui mérite d'être maîtrisée.

## FAQ

### Puis-je utiliser des chemins réseau pour les dossiers de polices ?
Oui, vous pouvez utiliser des chemins réseau pour vos dossiers de polices. Assurez-vous simplement que les chemins sont accessibles depuis votre application.

### Que se passe-t-il si une police est manquante dans les dossiers spécifiés ?
Si une police est manquante, Aspose.Words reviendra à la police par défaut spécifiée ou utilisera une police de remplacement.

### Puis-je ajouter des dossiers de polices sans remplacer les polices système ?
 Absolument! Utiliser`FontSettings.GetFontSources` pour récupérer les sources existantes et les combiner avec vos dossiers personnalisés en utilisant`FontSettings.SetFontSources`.

### Y a-t-il une limite au nombre de dossiers de polices que je peux ajouter ?
Il n'y a pas de limite stricte au nombre de dossiers de polices. Cependant, soyez attentif aux performances, car un plus grand nombre de dossiers peut augmenter les temps de chargement des polices.

### Comment puis-je vérifier quelles polices sont utilisées dans mon document ?
 Vous pouvez utiliser le`FontSettings.GetFontsSources` méthode pour récupérer et inspecter les sources de polices actuellement définies pour votre document.