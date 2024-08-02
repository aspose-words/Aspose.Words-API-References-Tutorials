---
title: Ajouter un filigrane de texte avec des options spécifiques
linktitle: Ajouter un filigrane de texte avec des options spécifiques
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter un filigrane de texte avec des options spécifiques à vos documents Word à l'aide d'Aspose.Words pour .NET. Personnalisez facilement la police, la taille, la couleur et la mise en page.
type: docs
weight: 10
url: /fr/net/programming-with-watermark/add-text-watermark-with-specific-options/
---
## Introduction

Les filigranes peuvent être un ajout élégant et fonctionnel à vos documents Word, allant du marquage des documents comme confidentiels à l'ajout d'une touche personnalisée. Dans ce didacticiel, nous verrons comment ajouter un filigrane de texte à un document Word à l'aide d'Aspose.Words pour .NET. Nous aborderons les options spécifiques que vous pouvez configurer, telles que la famille de polices, la taille de la police, la couleur et la mise en page. À la fin, vous pourrez personnaliser le filigrane de votre document pour l'adapter exactement à vos besoins. Alors, prenez votre éditeur de code et commençons !

## Conditions préalables

Avant de commencer, assurez-vous d'avoir mis en place les éléments suivants :

1.  Bibliothèque Aspose.Words pour .NET : vous devrez installer la bibliothèque Aspose.Words. Si vous ne l'avez pas déjà fait, vous pouvez le télécharger depuis le[Lien de téléchargement Aspose.Words](https://releases.aspose.com/words/net/).
2. Compréhension de base de C# : ce didacticiel utilisera C# comme langage de programmation. Une compréhension fondamentale de la syntaxe C# sera utile.
3. Environnement de développement .NET : assurez-vous d'avoir configuré un environnement de développement (comme Visual Studio) dans lequel vous pouvez créer et exécuter vos applications .NET.

## Importer des espaces de noms

Pour travailler avec Aspose.Words, vous devrez inclure les espaces de noms nécessaires dans votre projet. Voici ce que vous devez importer :

```csharp
using Aspose.Words;
using Aspose.Words.Rendering;
using System.Drawing;
```

## Étape 1 : Configurez votre document

 Tout d'abord, vous devez charger le document avec lequel vous souhaitez travailler. Pour ce didacticiel, nous utiliserons un exemple de document nommé`Document.docx`. Assurez-vous que ce document existe dans votre répertoire spécifié.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Dans cette étape, vous définissez le répertoire où se trouve votre document et le chargez dans une instance du`Document` classe.

## Étape 2 : configurer les options de filigrane

Ensuite, configurez les options de votre filigrane de texte. Vous pouvez personnaliser divers aspects, tels que la famille de polices, la taille de la police, la couleur et la mise en page. Configurons ces options.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
    FontFamily = "Arial",
    FontSize = 36,
    Color = Color.Black,
    Layout = WatermarkLayout.Horizontal,
    IsSemitrasparent = false
};
```

Voici ce que fait chaque option :
- `FontFamily`: Spécifie la police du texte du filigrane.
- `FontSize`: Définit la taille du texte du filigrane.
- `Color`: Définit la couleur du texte du filigrane.
- `Layout`Détermine l'orientation du filigrane (horizontale ou diagonale).
- `IsSemitrasparent`: Définit si le filigrane est semi-transparent.

## Étape 3 : ajouter le texte du filigrane

Maintenant, appliquez le filigrane à votre document en utilisant les options précédemment configurées. Dans cette étape, vous définirez le texte du filigrane sur « Test » et appliquerez les options que vous avez définies.

```csharp
doc.Watermark.SetText("Test", options);
```

Cette ligne de code ajoute le filigrane avec le texte « Test » au document, en appliquant les options spécifiées.

## Étape 4 : Enregistrez le document

Enfin, enregistrez le document avec le nouveau filigrane appliqué. Vous pouvez l'enregistrer sous un nouveau nom pour éviter d'écraser le document original.

```csharp
doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

Cet extrait de code enregistre le document modifié dans le même répertoire avec un nouveau nom de fichier.

## Conclusion

L'ajout d'un filigrane de texte à vos documents Word à l'aide d'Aspose.Words pour .NET est un processus simple lorsque vous le divisez en étapes gérables. En suivant ce didacticiel, vous avez appris à configurer diverses options de filigrane, notamment la police, la taille, la couleur, la mise en page et la transparence. Grâce à ces compétences, vous pouvez désormais personnaliser vos documents pour mieux répondre à vos besoins ou pour y inclure des informations essentielles telles que la confidentialité ou le branding.

 Si vous avez des questions ou avez besoin d'aide supplémentaire, n'hésitez pas à consulter le[Documentation Aspose.Words](https://reference.aspose.com/words/net/) ou visitez le[Forum d'assistance Aspose](https://forum.aspose.com/c/words/8) pour plus d'aide.

## FAQ

### Puis-je utiliser différentes polices pour le filigrane ?

 Oui, vous pouvez choisir n'importe quelle police installée sur votre système en spécifiant la`FontFamily` propriété dans le`TextWatermarkOptions`.

### Comment changer la couleur du filigrane ?

 Vous pouvez changer la couleur du filigrane en réglant le`Color` propriété dans le`TextWatermarkOptions` à n'importe qui`System.Drawing.Color` valeur.

### Est-il possible d'ajouter plusieurs filigranes à un document ?

Aspose.Words prend en charge l'ajout d'un filigrane à la fois. Pour ajouter plusieurs filigranes, vous devrez les créer et les appliquer séquentiellement.

### Puis-je ajuster la position du filigrane ?

 Le`WatermarkLayout`La propriété détermine l'orientation, mais les ajustements de positionnement précis ne sont pas directement pris en charge. Vous devrez peut-être utiliser d'autres techniques pour un placement exact.

### Que faire si j'ai besoin d'un filigrane semi-transparent ?

 Met le`IsSemitrasparent`propriété à`true` pour rendre votre filigrane semi-transparent.