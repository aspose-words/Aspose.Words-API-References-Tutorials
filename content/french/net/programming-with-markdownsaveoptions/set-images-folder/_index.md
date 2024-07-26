---
title: Définir le dossier d'images
linktitle: Définir le dossier d'images
second_title: API de traitement de documents Aspose.Words
description: Convertissez des documents Word en Markdown avec un alignement approprié des tableaux à l'aide d'Aspose.Words pour .NET. Suivez notre guide détaillé pour des résultats parfaits.
type: docs
weight: 10
url: /fr/net/programming-with-markdownsaveoptions/set-images-folder/
---
## Introduction

Avez-vous déjà eu envie d'exporter votre document Word au format Markdown tout en vous assurant que les tableaux et le contenu s'alignent parfaitement ? Aspose.Words for .NET est votre solution incontournable pour cette tâche. Dans cet article, nous vous guiderons tout au long du processus de configuration d'Aspose.Words, de préparation de votre document et de son exportation dans Markdown avec un alignement approprié du contenu du tableau. Nous décomposerons chaque étape pour la rendre facile à suivre et à comprendre. Alors, plongeons-nous et transformons vos documents Word en fichiers Markdown magnifiquement alignés !

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

-  Aspose.Words pour .NET : vous pouvez le télécharger[ici](https://releases.aspose.com/words/net/).
-  Une licence valide : obtenez un essai gratuit[ici](https://releases.aspose.com/) ou un permis temporaire[ici](https://purchase.aspose.com/temporary-license/).
- Visual Studio : ou tout autre IDE prenant en charge le développement .NET.
- Connaissance de base de C# : Compréhension du langage de programmation C#.

## Importer des espaces de noms

Pour commencer, vous devrez importer les espaces de noms nécessaires dans votre projet C#. Ces espaces de noms vous permettront d'accéder à la fonctionnalité Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using System.IO;
```

## Étape 1 : Configurez votre projet

Tout d’abord, configurez votre projet .NET dans votre IDE. Créez une nouvelle application console et ajoutez une référence à Aspose.Words pour .NET.

### 1.1 Créer un nouveau projet

Ouvrez Visual Studio et créez un nouveau projet d'application console. Nommez-le "MarkdownExporter" ou quelque chose de similaire.

### 1.2 Ajouter une référence Aspose.Words

 Pour ajouter Aspose.Words à votre projet, vous pouvez soit télécharger la DLL depuis le[Site Aspose](https://releases.aspose.com/words/net/) et ajoutez-le manuellement, ou utilisez NuGet Package Manager :

```bash
Install-Package Aspose.Words
```

## Étape 2 : Écrivez le code à exporter en tant que Markdown

Maintenant, écrivons le code pour lire le document Word et enregistrons-le en tant que fichier Markdown avec un alignement de tableau approprié.

### 2.1 Définissez le chemin d'accès à votre document

Définissez le chemin d'accès à votre document Word et le dossier dans lequel vous souhaitez enregistrer les images.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
```

### 2.2 Charger le document

Chargez votre document Word à l'aide d'Aspose.Words.

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

### 2.3 Configurer les options d'enregistrement Markdown

 Configurez le`MarkdownSaveOptions` pour spécifier où les images doivent être stockées.

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    ImagesFolder = dataDir + "Images"
};
```

### 2.4 Enregistrez le document en tant que Markdown

 Utiliser un`MemoryStream` pour enregistrer le document au format Markdown.

```csharp
using (MemoryStream stream = new MemoryStream())
{
    doc.Save(stream, saveOptions);
}
```

## Conclusion

L'exportation d'un document Word vers Markdown avec alignement du contenu du tableau à l'aide d'Aspose.Words for .NET est simple lorsque vous suivez ces étapes. Avec quelques lignes de code, vous pouvez automatiser le processus de conversion et vous assurer que votre contenu est bien formaté. Désormais, vous pouvez facilement partager vos documents au format Markdown, sachant qu'ils auront fière allure et conserveront leur structure.

## FAQ

### Puis-je utiliser Aspose.Words pour .NET avec d’autres langages de programmation ?

Oui, Aspose.Words for .NET peut être utilisé avec n'importe quel langage compatible .NET tel que VB.NET, F#, etc.

### Comment puis-je obtenir une licence temporaire pour Aspose.Words ?

 Vous pouvez obtenir un permis temporaire[ici](https://purchase.aspose.com/temporary-license/).

### Quels types de documents puis-je convertir en Markdown ?

Vous pouvez convertir divers documents Word, notamment .doc, .docx, .rtf, etc.

### Y a-t-il des limitations dans la version d’essai d’Aspose.Words ?

La version d'essai présente certaines limitations telles que des filigranes dans les fichiers de sortie. Vous pouvez obtenir un essai gratuit[ici](https://releases.aspose.com/).

### Où puis-je trouver plus d’exemples et de documentation pour Aspose.Words ?

 Vous pouvez trouver une documentation détaillée et des exemples sur le[Site Aspose](https://reference.aspose.com/words/net/).
