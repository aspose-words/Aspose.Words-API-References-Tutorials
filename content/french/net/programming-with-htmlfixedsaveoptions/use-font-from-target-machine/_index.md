---
title: Utiliser la police de la machine cible
linktitle: Utiliser la police de la machine cible
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment convertir un document Word en HTML fixe à l'aide des polices de la machine cible avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Lors de la conversion d'un document Word en HTML fixe dans une application C#, vous souhaiterez peut-être utiliser les polices de la machine cible pour garantir que le HTML rendu conserve l'apparence et le style d'origine du document. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement spécifier cette fonctionnalité à l'aide des options de sauvegarde HtmlFixedSaveOptions. Dans ce guide étape par étape, nous vous expliquerons comment utiliser le code source C# d'Aspose.Words pour .NET pour convertir un document Word en HTML fixe à l'aide des polices de la machine cible à l'aide de HtmlFixedSaveOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, dont .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification du formatage, l'ajout de sections et bien plus encore.

## Chargement du document Word

La première étape consiste à charger le document Word que vous souhaitez convertir en HTML fixe. Utilisez la classe Document pour charger le document à partir du fichier source. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

Dans cet exemple, nous chargeons le document "Bullet points with alternative font.docx" situé dans le répertoire documents.

## Configuration des options de sauvegarde

L'étape suivante consiste à configurer les options d'enregistrement pour la conversion en HTML fixe. Utilisez la classe HtmlFixedSaveOptions et définissez la propriété UseTargetMachineFonts sur true pour indiquer à Aspose.Words d'utiliser les polices de la machine cible. Voici comment procéder :

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Nous créons un nouvel objet HtmlFixedSaveOptions et définissons la propriété UseTargetMachineFonts sur true pour utiliser les polices de la machine cible lors de la conversion.

## Correction de la conversion de documents HTML

Maintenant que nous avons configuré les options de sauvegarde, nous pouvons procéder à la conversion du document en HTML fixe. Utilisez la méthode Save de la classe Document pour enregistrer le document converti au format HTML fixe en spécifiant les options d'enregistrement. Voici un exemple :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

Dans cet exemple, nous enregistrons le document converti sous le nom « WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html » en utilisant les options d'enregistrement spécifiées.

### Exemple de code source pour HtmlFixedSaveOptions avec la fonctionnalité « Utiliser les polices de la machine cible » utilisant Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document Word
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// Configurez les options de sauvegarde avec la fonctionnalité « Utiliser les polices de la machine cible »
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Convertir le document en HTML fixe
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment convertir un document Word en HTML fixe à l'aide des polices de la machine cible avec la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. La conversion en HTML fixe avec les polices de la machine cible garantit un rendu fidèle et cohérent du document au format HTML.
