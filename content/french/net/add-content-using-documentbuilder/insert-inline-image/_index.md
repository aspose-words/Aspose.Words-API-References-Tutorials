---
title: Insérer une image en ligne dans un document Word
linktitle: Insérer une image en ligne dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer des images en ligne dans des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-inline-image/
---
Dans ce didacticiel complet, vous apprendrez à insérer des images en ligne dans un document Word à l'aide d'Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous pourrez ajouter des images directement dans le texte de vos documents.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : Créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer une image en ligne
Ensuite, utilisez la méthode InsertImage de la classe DocumentBuilder pour insérer une image en ligne dans le document. Fournissez le chemin du fichier image en paramètre :

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Étape 3 : Enregistrez le document
Après avoir inséré l'image en ligne, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Exemple de code source pour insérer une image en ligne à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour insérer une image en ligne à l'aide d'Aspose.Words pour .NET :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment insérer des images en ligne dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais ajouter des images de manière transparente dans le texte de vos documents.

Les images en ligne sont utiles pour divers scénarios, tels que l'ajout d'illustrations, de logos ou d'autres éléments visuels directement dans le flux du document.

### FAQ pour insérer une image en ligne dans un document Word

#### Q : Puis-je redimensionner les images en ligne dans le document Word ?

R : Oui, vous pouvez redimensionner les images en ligne à l'aide d'Aspose.Words for .NET. Après avoir inséré l'image, vous pouvez manipuler sa taille en ajustant les propriétés de largeur et de hauteur de l'objet Shape représentant l'image.

#### Q : Est-il possible d'ajouter du texte alternatif aux images en ligne à des fins d'accessibilité ?

R : Oui, vous pouvez ajouter du texte alternatif aux images en ligne pour améliorer l'accessibilité. Aspose.Words for .NET prend en charge l'ajout de texte alternatif aux images, permettant aux lecteurs d'écran et à d'autres technologies d'assistance de décrire le contenu de l'image aux utilisateurs malvoyants.

#### Q : Puis-je appliquer un formatage ou des styles aux images en ligne ?

R : Absolument ! Aspose.Words for .NET fournit des options de formatage étendues pour les images en ligne. Vous pouvez appliquer divers styles, bordures, effets et autres attributs de mise en forme aux images pour correspondre à la conception visuelle de votre document.

#### Q : Aspose.Words for .NET prend-il en charge l'insertion d'images à partir d'un flux ou d'un tableau d'octets ?

R : Oui, vous pouvez insérer des images en ligne à partir de flux ou de tableaux d'octets à l'aide d'Aspose.Words pour .NET. Cela vous permet de travailler avec des images chargées à partir de sources externes ou des images générées dynamiquement.

#### Q : Puis-je insérer des images à des endroits spécifiques dans le contenu du texte ?

: Oui, la classe DocumentBuilder dans Aspose.Words pour .NET fournit un contrôle précis sur la position d'insertion des images en ligne. Vous pouvez spécifier l'emplacement exact dans le texte où l'image doit être insérée.