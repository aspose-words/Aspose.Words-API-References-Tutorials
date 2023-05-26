---
title: Obtenir la plage de pages Tiff
linktitle: Obtenir la plage de pages Tiff
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à extraire une gamme de pages TIFF avec Aspose.Words pour .NET. Tutoriel complet pour les fichiers TIFF personnalisés.
type: docs
weight: 10
url: /fr/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

Dans ce didacticiel, nous allons explorer le code source C # fourni pour obtenir une gamme de pages TIFF avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'extraire une plage spécifique de pages d'un document et de les enregistrer sous forme de fichier TIFF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words pour .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Chargement du document

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Dans cette étape, nous chargeons le document en utilisant le`Document` méthode et en passant le chemin vers le fichier DOCX à charger.

## Étape 3 : Enregistrer le document complet au format TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

 Dans cette étape, nous enregistrons le document complet au format TIFF en utilisant le`Save` méthode et en spécifiant le chemin d'accès au fichier de sortie avec l'extension`.tiff`.

## Étape 4 : Configurer les options de sauvegarde pour la plage de pages

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 Dans cette étape, nous configurons les options de sauvegarde pour la plage de pages spécifique. Nous créons un nouveau`ImageSaveOptions` objet spécifiant le format de sauvegarde souhaité, ici "Tiff" pour le format TIFF. Nous utilisons`PageSet` pour préciser la plage de pages que l'on souhaite extraire, ici de la page 0 à la page 1 (incluse). Nous avons également défini la compression TIFF sur`Ccitt4` et la résolution à 160 dpi.

## Étape 5 : Enregistrer la plage de pages au format TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 Dans cette dernière étape, nous enregistrons la plage de pages spécifiée au format TIFF à l'aide de la`Save`méthode et en passant le chemin vers le fichier de sortie avec`.tiff` extension, ainsi que les options d'enregistrement spécifiées.

Vous pouvez maintenant exécuter le code source pour obtenir une plage spécifique de pages de votre document et les enregistrer en tant que fichier TIFF. Les fichiers résultants seront enregistrés dans le répertoire spécifié avec les noms "WorkingWithImageSaveOptions.MultipageTiff.tiff" pour le document complet et "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" pour la plage de pages spécifiée.

### Exemple de code source de Get Tiff Page Range en utilisant Aspose.Words pour .NET

```csharp 

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité d'obtention d'une gamme de pages TIFF avec Aspose.Words pour .NET. Nous avons appris à extraire une plage spécifique de pages d'un document et à les enregistrer sous forme de fichier TIFF.

Cette fonctionnalité est utile lorsque vous souhaitez extraire uniquement certaines pages d'un document et les enregistrer dans un format d'image standard tel que TIFF. Vous pouvez également personnaliser les options de compression et de résolution pour obtenir des fichiers TIFF de la meilleure qualité.

Aspose.Words pour .NET offre une vaste gamme de fonctionnalités avancées pour la manipulation et la génération de documents. Obtenir une plage de pages TIFF est l'un des nombreux outils puissants qu'il met à votre disposition.

N'hésitez pas à intégrer cette fonctionnalité dans vos projets Aspose.Words for .NET pour extraire et enregistrer des plages spécifiques de pages de vos documents au format TIFF.