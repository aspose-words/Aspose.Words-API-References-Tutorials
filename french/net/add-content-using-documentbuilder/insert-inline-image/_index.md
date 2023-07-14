---
title: Insérer une image en ligne
linktitle: Insérer une image en ligne
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer des images en ligne dans des documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-inline-image/
---

Dans ce didacticiel complet, vous apprendrez à insérer des images en ligne dans un document Word à l'aide d'Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure d'ajouter des images directement dans le texte de vos documents.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer une image en ligne
Ensuite, utilisez la méthode InsertImage de la classe DocumentBuilder pour insérer une image en ligne dans le document. Indiquez le chemin du fichier image en tant que paramètre :

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Étape 3 : Enregistrer le document
Après avoir inséré l'image en ligne, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

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
Toutes nos félicitations! Vous avez appris avec succès comment insérer des images en ligne dans un document Word en utilisant Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais ajouter des images de manière transparente dans le texte de vos documents.

Les images en ligne sont utiles pour divers scénarios, tels que l'ajout d'illustrations, de logos ou d'autres éléments visuels directement dans le flux du document.
