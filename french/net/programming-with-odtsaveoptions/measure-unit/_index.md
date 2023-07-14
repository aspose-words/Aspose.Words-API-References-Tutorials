---
title: Unité de mesure
linktitle: Unité de mesure
second_title: API de traitement de documents Aspose.Words
description: Apprenez à spécifier l'unité de mesure lors de la conversion d'un document Word en ODT avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-odtsaveoptions/measure-unit/
---

Lorsque vous convertissez un document Word au format OpenDocument Text (ODT) dans une application C#, vous pouvez spécifier l'unité de mesure utilisée pour la mise en forme mesurable et les propriétés de contenu. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement spécifier cette fonctionnalité à l'aide des options d'enregistrement OdtSaveOptions. Dans ce guide étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour le code source .NET C# pour convertir un document Word en ODT en spécifiant l'unité de mesure à l'aide d'OdtSaveOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, y compris .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification de la mise en forme, l'ajout de sections et bien plus encore.

## Chargement du document Word

La première étape consiste à charger le document Word que vous souhaitez convertir en ODT. Utilisez la classe Document pour charger le document à partir du fichier source. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Dans cet exemple, nous chargeons le document "Document.docx" situé dans le répertoire des documents.

## Configuration des options de sauvegarde

L'étape suivante consiste à configurer les options de sauvegarde pour la conversion en ODT. Utilisez la classe OdtSaveOptions et définissez la propriété MeasureUnit sur la valeur souhaitée. Par exemple, si vous souhaitez utiliser les pouces comme unité de mesure, définissez MeasureUnit sur OdtSaveMeasureUnit.Inches. Voici comment procéder :

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Nous créons un nouvel objet OdtSaveOptions et définissons la propriété MeasureUnit sur la valeur souhaitée, dans notre cas, OdtSaveMeasureUnit.Inches pour utiliser les pouces comme unité de mesure.

## Convertir un document en ODT

Maintenant que nous avons configuré les options de sauvegarde, nous pouvons procéder à la conversion du document en ODT. Utilisez la méthode Save de la classe Document pour enregistrer le document converti au format ODT en spécifiant les options d'enregistrement. Voici un exemple :

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Dans cet exemple, nous enregistrons le document converti sous "WorkingWithOdtSaveOptions.MeasureUnit.odt" en utilisant les options d'enregistrement spécifiées.

### Exemple de code source pour OdtSaveOptions avec la fonctionnalité "Unité de mesure" utilisant Aspose.Words pour .NET



```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document Word
Document doc = new Document(dataDir + "Document.docx");

// Configuration des options de sauvegarde avec la fonctionnalité "Unité de mesure"
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Convertir le document en ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment convertir un document Word en ODT en spécifiant l'unité de mesure à l'aide des options d'enregistrement OdtSaveOptions avec la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. La spécification de l'unité de mesure lors de la conversion en ODT vous permet de contrôler la mise en forme et les dimensions du document résultant en fonction de vos besoins spécifiques.