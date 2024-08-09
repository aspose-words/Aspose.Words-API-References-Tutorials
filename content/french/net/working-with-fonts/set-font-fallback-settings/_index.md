---
title: Définir les paramètres de secours des polices
linktitle: Définir les paramètres de secours des polices
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment configurer les paramètres de secours des polices dans Aspose.Words pour .NET. Ce guide complet garantit que tous les caractères de vos documents sont affichés correctement.
type: docs
weight: 10
url: /fr/net/working-with-fonts/set-font-fallback-settings/
---
## Introduction

Lorsque vous travaillez avec des documents contenant divers éléments de texte, tels que différentes langues ou caractères spéciaux, il est crucial de garantir que ces éléments s'affichent correctement. Aspose.Words for .NET offre une fonctionnalité puissante appelée Paramètres de secours des polices, qui aide à définir des règles de substitution des polices lorsque la police d'origine ne prend pas en charge certains caractères. Dans ce guide, nous explorerons comment configurer les paramètres de secours des polices à l'aide d'Aspose.Words pour .NET dans un didacticiel étape par étape.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

- Connaissance de base de C# : Familiarité avec le langage de programmation C# et le framework .NET.
-  Aspose.Words pour .NET : téléchargez et installez à partir du[lien de téléchargement](https://releases.aspose.com/words/net/).
- Environnement de développement : une configuration comme Visual Studio pour écrire et exécuter votre code.
-  Exemple de document : ayez un exemple de document (par exemple,`Rendering.docx`) prêt à être testé.
- Règles de secours des polices XML : préparez un fichier XML définissant les règles de secours des polices.

## Importer des espaces de noms

Pour utiliser Aspose.Words, vous devez importer les espaces de noms nécessaires. Cela permet d'accéder à diverses classes et méthodes requises pour le traitement des documents.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## Étape 1 : Définir le répertoire des documents

Tout d’abord, définissez le répertoire dans lequel votre document est stocké. Ceci est essentiel pour localiser et traiter votre document.

```csharp
// Le chemin d'accès au répertoire des documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le document

 Chargez votre document dans un Aspose.Words`Document` objet. Cette étape vous permet de travailler avec le document par programmation.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : configurer les paramètres de police

 Créer un nouveau`FontSettings` objet et chargez les paramètres de secours de la police à partir d’un fichier XML. Ce fichier XML contient les règles de repli des polices.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## Étape 4 : appliquer les paramètres de police au document

 Attribuer le configuré`FontSettings`au document. Cela garantit que les règles de remplacement des polices sont appliquées lors du rendu du document.

```csharp
doc.FontSettings = fontSettings;
```

## Étape 5 : Enregistrez le document

Enfin, enregistrez le document. Les paramètres de secours des polices seront utilisés lors de l’opération de sauvegarde pour garantir une substitution de police appropriée.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Fichier XML : règles de remplacement des polices

Voici un exemple de ce à quoi devrait ressembler votre fichier XML définissant les règles de remplacement des polices :

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## Conclusion

En suivant ces étapes, vous pouvez configurer et utiliser efficacement les paramètres de secours des polices dans Aspose.Words pour .NET. Cela garantit que vos documents affichent correctement tous les caractères, même si la police d'origine ne prend pas en charge certains caractères. La mise en œuvre de ces paramètres améliorera considérablement la qualité et la lisibilité de vos documents.

## FAQ

### Q1 : Qu'est-ce que le remplacement des polices ?

Font Fallback est une fonctionnalité qui permet de remplacer des polices lorsque la police d'origine ne prend pas en charge certains caractères, garantissant ainsi un affichage correct de tous les éléments de texte.

### Q2 : Puis-je spécifier plusieurs polices de secours ?

Oui, vous pouvez spécifier plusieurs polices de secours dans les règles XML. Aspose.Words vérifiera chaque police dans l'ordre spécifié jusqu'à ce qu'il en trouve une qui prend en charge le caractère.

### Q3 : Où puis-je télécharger Aspose.Words pour .NET ?

 Vous pouvez le télécharger depuis le[Aspose la page de téléchargement](https://releases.aspose.com/words/net/).

### Q4 : Comment créer le fichier XML pour les règles de remplacement des polices ?

Le fichier XML peut être créé à l'aide de n'importe quel éditeur de texte. Il doit suivre la structure présentée dans l'exemple fourni dans ce didacticiel.

### Q5 : Existe-t-il une assistance disponible pour Aspose.Words ?

 Oui, vous pouvez trouver de l'aide sur le[Forum d'assistance Aspose.Words](https://forum.aspose.com/c/words/8).