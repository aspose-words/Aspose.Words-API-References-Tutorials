---
title: Insérer une image flottante
linktitle: Insérer une image flottante
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer des images flottantes dans des documents Word à l'aide d'Aspose.Words pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/insert-floating-image/
---

Dans cet exemple complet, vous apprendrez à insérer une image flottante dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure d'ajouter des images avec des options de positionnement et d'habillage personnalisables à vos documents.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document et DocumentBuilder
Pour commencer, créez un nouveau document à l'aide de la classe Document et initialisez un objet DocumentBuilder :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer une image flottante
Ensuite, utilisez la méthode InsertImage de la classe DocumentBuilder pour insérer une image flottante. Fournissez le chemin du fichier image, la position horizontale et verticale relative, la largeur, la hauteur et les options d'habillage en tant que paramètres :

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Étape 3 : Enregistrer le document
Après avoir inséré l'image flottante, enregistrez le document dans un fichier à l'aide de la méthode Save de la classe Document :

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Exemple de code source pour insérer une image flottante à l'aide de Aspose.Words pour .NET
Voici le code source complet pour insérer une image flottante en utilisant Aspose.Words pour .NET :
Les images flottantes sont utiles pour divers scénarios, tels que l'ajout de logos, d'illustrations ou d'éléments décoratifs pouvant être positionnés indépendamment du texte du document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

N'oubliez pas d'ajuster le code en fonction de vos besoins spécifiques, y compris le chemin du fichier image et les options de positionnement et d'habillage souhaitées.

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment insérer une image flottante dans un document Word en utilisant Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais améliorer vos documents avec des images flottantes visuellement attrayantes et personnalisables.

