---
title: Spécifier la police par défaut lors du rendu
linktitle: Spécifier la police par défaut lors du rendu
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment spécifier une police par défaut lors du rendu de documents Word à l'aide d'Aspose.Words for .NET. Garantissez une apparence cohérente des documents sur toutes les plateformes.
type: docs
weight: 10
url: /fr/net/working-with-fonts/specify-default-font-when-rendering/
---
## Introduction

S'assurer que vos documents Word s'affichent correctement sur différentes plates-formes peut être un défi, en particulier en ce qui concerne la compatibilité des polices. Une façon de conserver une apparence cohérente consiste à spécifier une police par défaut lors du rendu de vos documents au format PDF ou dans d'autres formats. Dans ce didacticiel, nous verrons comment définir une police par défaut à l'aide d'Aspose.Words pour .NET, afin que vos documents aient fière allure, quel que soit l'endroit où ils sont affichés.

## Conditions préalables

Avant de plonger dans le code, expliquons ce que vous devrez suivre avec ce didacticiel :

- Aspose.Words pour .NET : assurez-vous que la dernière version est installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/words/net/).
- Environnement de développement : Visual Studio ou tout autre environnement de développement .NET.
- Connaissance de base de C# : ce didacticiel suppose que vous êtes à l'aise avec la programmation C#.

## Importer des espaces de noms

Pour commencer, vous devez importer les espaces de noms nécessaires. Ceux-ci vous permettront d'accéder aux classes et méthodes nécessaires pour travailler avec Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Maintenant, décomposons le processus de spécification d'une police par défaut en étapes faciles à suivre.

## Étape 1 : Configurez votre répertoire de documents

Tout d’abord, définissez le chemin d’accès à votre répertoire de documents. C'est ici que vos fichiers d'entrée et de sortie seront stockés.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez votre document

Ensuite, chargez le document que vous souhaitez restituer. Dans cet exemple, nous utiliserons un fichier nommé « Rendering.docx ».

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : configurer les paramètres de police

 Créer une instance de`FontSettings` et spécifiez la police par défaut. Si la police définie est introuvable lors du rendu, Aspose.Words utilisera la police disponible la plus proche sur la machine.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
```

## Étape 4 : appliquer les paramètres de police au document

Attribuez les paramètres de police configurés à votre document.

```csharp
doc.FontSettings = fontSettings;
```

## Étape 5 : Enregistrez le document

Enfin, enregistrez le document au format souhaité. Dans ce cas, nous l'enregistrerons au format PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Conclusion

En suivant ces étapes, vous pouvez vous assurer que vos documents Word s'affichent avec une police par défaut spécifiée, en maintenant la cohérence sur les différentes plates-formes. Cela peut être particulièrement utile pour les documents largement partagés ou visualisés sur des systèmes avec différentes polices disponibles.


## FAQ

### Pourquoi spécifier une police par défaut dans Aspose.Words ?
La spécification d'une police par défaut garantit que votre document apparaît cohérent sur différentes plates-formes, même si les polices d'origine ne sont pas disponibles.

### Que se passe-t-il si la police par défaut n'est pas trouvée lors du rendu ?
Aspose.Words utilisera la police disponible la plus proche sur la machine pour conserver l'apparence du document aussi fidèlement que possible.

### Puis-je spécifier plusieurs polices par défaut ?
 Non, vous ne pouvez spécifier qu'une seule police par défaut. Cependant, vous pouvez gérer la substitution de polices dans des cas spécifiques à l'aide de l'option`FontSettings` classe.

### Aspose.Words for .NET est-il compatible avec toutes les versions de documents Word ?
Oui, Aspose.Words for .NET prend en charge un large éventail de formats de documents Word, notamment DOC, DOCX, RTF, etc.

### Où puis-je obtenir de l'aide si je rencontre des problèmes ?
 Vous pouvez obtenir l'assistance de la communauté Aspose et des développeurs sur le[Forum d'assistance Aspose.Words](https://forum.aspose.com/c/words/8).