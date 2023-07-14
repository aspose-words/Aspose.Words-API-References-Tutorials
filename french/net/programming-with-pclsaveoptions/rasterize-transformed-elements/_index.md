---
title: Pixelliser les éléments transformés
linktitle: Pixelliser les éléments transformés
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment désactiver la rastérisation des éléments transformés lors de la conversion au format PCL avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words pour .NET est une bibliothèque puissante pour créer, manipuler et convertir des documents Word dans une application C#. Parmi les fonctionnalités offertes par Aspose.Words figure la possibilité de pixelliser les éléments transformés lors de la conversion de documents en différents formats. Dans ce guide, nous allons vous montrer comment utiliser le code source C# de Aspose.Words pour .NET pour désactiver la rastérisation des éléments transformés lors de la conversion d'un document au format PCL.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque populaire qui rend le traitement de mots avec des documents Word simple et efficace. Il offre un large éventail de fonctionnalités pour la création, l'édition et la conversion de documents Word, y compris la prise en charge de la pixellisation des éléments transformés lors de la conversion.

## Chargement du document Word

La première étape consiste à charger le document Word que vous souhaitez convertir au format PCL. Utilisez la classe Document pour charger le document à partir du fichier source. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Dans cet exemple, nous chargeons le document "Rendering.docx" situé dans le répertoire des documents.

## Configuration des options de sauvegarde

L'étape suivante consiste à configurer les options d'enregistrement pour la conversion au format PCL. Utilisez la classe PclSaveOptions et définissez la propriété RasterizeTransformedElements sur false. Voici comment procéder :

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

Nous créons un nouvel objet PclSaveOptions et définissons la propriété SaveFormat sur SaveFormat.Pcl pour spécifier que nous voulons enregistrer le document au format PCL. Ensuite, nous définissons la propriété RasterizeTransformedElements sur false pour désactiver la rastérisation des éléments transformés.

## Conversion du document au format PCL

Maintenant que nous avons configuré les options de sauvegarde, nous pouvons procéder à la conversion du document au format PCL. Utilisez la méthode Save de la classe Document pour enregistrer le document converti au format PCL en spécifiant les options d'enregistrement. Voici un exemple :

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

Dans cet exemple, nous enregistrons le document converti sous "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" en utilisant les options d'enregistrement spécifiées.

### Exemple de code source pour la fonctionnalité "Rasterize Transformed Elements" avec Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document Word


Document doc = new Document(dataDir + "Rendering.docx");

// Configurer les options de sauvegarde pour la conversion au format PCL
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Convertir le document au format PCL
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser Aspose.Words pour .NET pour désactiver la rastérisation des éléments transformés lors de la conversion d'un document au format PCL à l'aide du code source C# fourni. En suivant les étapes fournies, vous pouvez facilement contrôler le comportement de pixellisation des éléments transformés lors de la conversion de vos documents Word en différents formats. Aspose.Words offre une flexibilité et une puissance considérables pour travailler avec les éléments transformés, vous permettant de créer des documents convertis précisément selon vos besoins spécifiques.