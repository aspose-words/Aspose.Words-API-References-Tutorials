---
title: Définir le dossier d'images
linktitle: Définir le dossier d'images
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir le dossier images lors de l'exportation vers Markdown avec Aspose.Words pour .NET. Personnalisez le placement des images pour une meilleure organisation et intégration.
type: docs
weight: 10
url: /fr/net/programming-with-markdownsaveoptions/set-images-folder/
---

Voici un guide étape par étape pour expliquer le code source C# suivant qui permet de définir le dossier d'images pour les options d'exportation Markdown à l'aide de la bibliothèque Aspose.Words pour .NET. Assurez-vous d'avoir inclus la bibliothèque Aspose.Words dans votre projet avant d'utiliser ce code.

## Étape 1 : Définir le chemin du répertoire du document

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Assurez-vous de spécifier le chemin correct vers votre répertoire de documents où se trouve le document contenant les images.

## Étape 2 : Charger le document contenant les images

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Nous chargeons le document spécifié qui contient les images que nous souhaitons exporter avec les options Markdown.

## Étape 3 : Définir le dossier d'images pour les options d'exportation Markdown

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Nous créons une instance de`MarkdownSaveOptions` et définissez le chemin d'accès au dossier images à l'aide du`ImagesFolder` propriété. Assurez-vous de spécifier le chemin correct vers le dossier dans lequel vous souhaitez enregistrer les images exportées.

## Étape 4 : Enregistrez le document avec les options d'exportation Markdown

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Nous enregistrons le document dans un flux mémoire en utilisant les options d'exportation Markdown spécifiées. Vous pouvez ensuite utiliser le flux pour effectuer d'autres opérations, telles que l'enregistrement du contenu Markdown dans un fichier.

### Exemple de code source pour définir le dossier images pour MarkdownSaveOptions avec Aspose.Words pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Ce code source montre comment charger un document contenant des images, puis définir le dossier images pour les options d'exportation Markdown. À l'aide des options spécifiées, le document est ensuite enregistré dans un flux mémoire. Cela vous permet de personnaliser l'emplacement du dossier images lors de l'exportation du contenu Markdown.