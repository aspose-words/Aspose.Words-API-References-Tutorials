---
title: Ignorer les images PDF
linktitle: Ignorer les images PDF
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à charger un document PDF sans charger les images PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-loadoptions/skip-pdf-images/
---

Lorsque vous travaillez avec des documents PDF dans une application C#, il peut être nécessaire d'ignorer le chargement des images PDF pour des raisons de performances ou de gestion de l'espace de stockage. Avec la bibliothèque Aspose.Words pour .NET, vous pouvez facilement ignorer le chargement des images PDF à l'aide des options de chargement PdfLoadOptions. Dans ce guide étape par étape, nous vous expliquerons comment utiliser le code source Aspose.Words pour .NET C# pour charger un document PDF en sautant le chargement des images PDF à l'aide des options de chargement PdfLoadOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, y compris .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification de la mise en forme, l'ajout de sections et bien plus encore.

## Configuration des options de chargement

La première étape consiste à configurer les options de chargement de notre document PDF. Utilisez la classe PdfLoadOptions pour spécifier les paramètres de chargement. Dans notre cas, nous devons définir la propriété SkipPdfImages sur true pour ignorer le chargement des images PDF. Voici comment procéder :

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { SkipPdfImages = true };
```

Nous créons un nouvel objet PdfLoadOptions et définissons la propriété SkipPdfImages sur true pour ignorer le chargement des images PDF.

## Charger le document PDF en sautant les images PDF

Maintenant que nous avons configuré les options de chargement, nous pouvons charger le document PDF à l'aide de la classe Document et spécifier les options de chargement. Voici un exemple :

```csharp
Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

Dans cet exemple, nous chargeons le document PDF "Pdf Document.pdf" situé dans le répertoire des documents en utilisant les options de chargement spécifiées.

### Exemple de code source pour PdfLoadOptions avec la fonctionnalité "Skip Pdf Images" utilisant Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configurez les options de chargement avec la fonction "Ignorer les images PDF"
PdfLoadOptions loadOptions = new PdfLoadOptions { SkipPdfImages = true };

// Charger le document PDF en sautant les images PDF
Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment charger un document PDF en sautant le chargement des images PDF à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. Ignorer le chargement des images PDF peut améliorer les performances et la gestion de l'espace de stockage lors du traitement des documents PDF.