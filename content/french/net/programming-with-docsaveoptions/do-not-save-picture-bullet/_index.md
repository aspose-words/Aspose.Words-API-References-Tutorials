---
title: Ne pas enregistrer la puce d'image
linktitle: Ne pas enregistrer la puce d'image
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment désactiver l’enregistrement des puces d’image dans les documents Word à l’aide d’Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Les puces illustrées sont une fonctionnalité couramment utilisée dans les documents Word pour ajouter des puces personnalisées. Cependant, dans certains cas, il peut être nécessaire de désactiver l'enregistrement des puces d'image lors de la manipulation de documents à l'aide de la bibliothèque Aspose.Words pour .NET. Dans ce guide étape par étape, nous expliquerons comment utiliser le code source Aspose.Words C# pour .NET pour désactiver l'enregistrement des puces d'image à l'aide des options d'enregistrement DocSaveOptions.

## Comprendre la bibliothèque Aspose.Words

Avant de plonger dans le code, il est important de comprendre la bibliothèque Aspose.Words pour .NET. Aspose.Words est une bibliothèque puissante pour créer, éditer, convertir et protéger des documents Word sur différentes plates-formes, dont .NET. Il offre de nombreuses fonctionnalités pour manipuler des documents, telles que l'insertion de texte, la modification du formatage, l'ajout de sections et bien plus encore.

## Étape 1 : Définition du répertoire des documents

La première étape consiste à définir le répertoire où se trouvent vos documents. Vous devez spécifier le chemin complet du répertoire. Par exemple :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel d'accès à votre répertoire de documents.

## Étape 2 : Chargement du document avec des puces d'image

Ensuite, vous devez charger le document avec des puces d'image. Utilisez la classe Document pour charger le document à partir d'un fichier. Par exemple :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Dans cet exemple, nous chargeons le document à partir du fichier "Image bullet points.docx".

  situé dans le répertoire des documents.

## Étape 3 : Configurer les options d'enregistrement

Configurons maintenant les options d'enregistrement de notre document. Utilisez la classe DocSaveOptions pour spécifier les paramètres de sauvegarde. Par exemple :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

Dans cet exemple, nous créons un nouvel objet DocSaveOptions et définissons la propriété SavePictureBullet sur false pour désactiver l'enregistrement des puces d'image.

## Étape 4 : Activer la fonctionnalité « Ne pas enregistrer la puce d'image »

Pour activer la fonctionnalité "Ne pas enregistrer Picture Bullet", nous avons déjà configuré les options d'enregistrement avec SavePictureBullet défini sur false. Cela garantit que les puces d'image ne sont pas enregistrées dans le document final.

## Étape 5 : Enregistrez le document

Enfin, vous pouvez enregistrer le document à l'aide de la méthode Save de la classe Document. Spécifiez le chemin complet du fichier et le nom de fichier souhaité. Par exemple :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Assurez-vous de remplacer "dataDir" par le chemin du répertoire de vos documents.

## Exemple de code source pour les options d'enregistrement DocSaveOptions avec la fonctionnalité "Ne pas enregistrer la puce d'image" à l'aide d'Aspose.Words pour .NET

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Charger le document avec des puces d'image
Document doc = new Document(dataDir + "Image bullet points.docx");

// Configurez les options d'enregistrement avec la fonctionnalité "Ne pas enregistrer l'image Bullet"
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Enregistrez le document avec les options spécifiées
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Conclusion

Dans ce guide, nous avons expliqué comment désactiver l'enregistrement des puces d'image dans un document à l'aide de la bibliothèque Aspose.Words pour .NET. En suivant les étapes fournies et en utilisant le code source C# fourni, vous pouvez facilement appliquer cette fonctionnalité dans votre application C#. La désactivation de l'enregistrement des puces d'image peut être utile dans certaines situations pour préserver la structure et le formatage du document sans enregistrer les puces d'image.