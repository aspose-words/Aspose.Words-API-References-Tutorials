---
title: Exporter des ressources
linktitle: Exporter des ressources
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment exporter des ressources telles que CSS et des polices tout en enregistrant des documents Word au format HTML à l'aide d'Aspose.Words pour .NET. Suivez notre guide étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-htmlsaveoptions/export-resources/
---
## Introduction

Salut, amis passionnés de technologie ! Si vous avez déjà eu besoin de convertir des documents Word en HTML, vous êtes au bon endroit. Aujourd'hui, nous plongeons dans le monde merveilleux d'Aspose.Words for .NET. Cette puissante bibliothèque facilite l'utilisation de documents Word par programmation. Dans ce didacticiel, nous passerons en revue les étapes d'exportation de ressources, telles que les polices et CSS, lors de l'enregistrement d'un document Word au format HTML à l'aide d'Aspose.Words pour .NET. Attachez votre ceinture pour une balade amusante et informative !

## Conditions préalables

Avant de plonger dans le code, assurons-nous que vous disposez de tout ce dont vous avez besoin pour commencer. Voici une liste de contrôle rapide :

1.  Visual Studio : assurez-vous que Visual Studio est installé sur votre ordinateur. Vous pouvez le télécharger depuis le[Site Web de Visual Studio](https://visualstudio.microsoft.com/).
2.  Aspose.Words for .NET : vous aurez besoin de la bibliothèque Aspose.Words for .NET. Si vous ne l'avez pas encore, profitez d'un essai gratuit sur[Aspose les versions](https://releases.aspose.com/words/net/) ou achetez-le chez[Boutique Aspose](https://purchase.aspose.com/buy).
3. Connaissance de base de C# : Une compréhension fondamentale de C# vous aidera à suivre les exemples de code.

Vous avez tout ça ? Super! Passons à l'importation des espaces de noms nécessaires.

## Importer des espaces de noms

Pour utiliser Aspose.Words pour .NET, vous devez inclure les espaces de noms pertinents dans votre projet. Voici comment procéder :

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Ces espaces de noms sont cruciaux pour accéder aux classes et méthodes Aspose.Words que nous utiliserons dans notre didacticiel.

Décomposons le processus d'exportation de ressources lors de l'enregistrement d'un document Word au format HTML. Nous allons procéder étape par étape, afin que ce soit facile à suivre.

## Étape 1 : Configurez votre répertoire de documents

Tout d’abord, vous devez spécifier le chemin d’accès à votre répertoire de documents. C'est ici que se trouve votre document Word et que le fichier HTML sera enregistré.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel de votre répertoire.

## Étape 2 : Charger le document Word

 Ensuite, chargeons le document Word que vous souhaitez convertir en HTML. Pour ce tutoriel, nous utiliserons un document nommé`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Cette ligne de code charge le document à partir du répertoire spécifié.

## Étape 3 : Configurer les options d'enregistrement HTML

Pour exporter des ressources telles que CSS et polices, vous devez configurer le`HtmlSaveOptions`. Cette étape est cruciale pour garantir que votre sortie HTML est bien structurée et inclut les ressources nécessaires.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://exemple.com/resources"
};
```

Décomposons ce que fait chaque option :
- `CssStyleSheetType = CssStyleSheetType.External`: Cette option spécifie que les styles CSS doivent être enregistrés dans une feuille de style externe.
- `ExportFontResources = true`: Cela permet l’exportation des ressources de polices.
- `ResourceFolder = dataDir + "Resources"`: Spécifie le dossier local dans lequel les ressources (comme les polices et les fichiers CSS) seront enregistrées.
- `ResourceFolderAlias = "http://example.com/resources"`: Définit un alias pour le dossier de ressources, qui sera utilisé dans le fichier HTML.

## Étape 4 : Enregistrez le document au format HTML

Une fois les options d'enregistrement configurées, la dernière étape consiste à enregistrer le document en tant que fichier HTML. Voici comment procéder :

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Cette ligne de code enregistre le document au format HTML, ainsi que les ressources exportées.

## Conclusion

Et voilà ! Vous avez exporté avec succès des ressources tout en enregistrant un document Word au format HTML à l'aide d'Aspose.Words pour .NET. Avec cette puissante bibliothèque, la gestion des documents Word par programmation devient un jeu d’enfant. Que vous travailliez sur une application Web ou que vous ayez simplement besoin de convertir des documents pour une utilisation hors ligne, Aspose.Words est là pour vous.

## FAQ

### Puis-je exporter des images avec des polices et du CSS ?
 Oui, vous pouvez ! Aspose.Words for .NET prend également en charge l'exportation d'images. Assurez-vous simplement de configurer le`HtmlSaveOptions` par conséquent.

### Existe-t-il un moyen d'intégrer du CSS au lieu d'utiliser une feuille de style externe ?
 Absolument. Vous pouvez définir`CssStyleSheetType` à`CssStyleSheetType.Embedded` si vous préférez les styles intégrés.

### Comment puis-je personnaliser le nom du fichier HTML de sortie ?
 Vous pouvez spécifier n'importe quel nom de fichier dans le champ`doc.Save` méthode. Par exemple,`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### Aspose.Words prend-il en charge d'autres formats que HTML ?
 Oui, il prend en charge divers formats, notamment PDF, DOCX, TXT, etc. Découvrez le[documentation](https://reference.aspose.com/words/net/) pour une liste complète.

### Où puis-je obtenir plus de soutien et de ressources ?
Pour plus d'aide, visitez le[Forum d'assistance Aspose.Words](https://forum.aspose.com/c/words/8) . Vous pouvez également trouver une documentation détaillée et des exemples sur le[Site Aspose](https://reference.aspose.com/words/net/).