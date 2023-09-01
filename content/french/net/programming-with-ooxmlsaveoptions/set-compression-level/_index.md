---
title: Définir le niveau de compression
linktitle: Définir le niveau de compression
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir le niveau de compression lors de l'enregistrement d'un document avec Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
Dans ce didacticiel, nous explorerons le code source C# fourni pour définir le niveau de compression lors de l'enregistrement d'un document à l'aide d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de contrôler le niveau de compression du document généré.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words for .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Chargement du document

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Dans cette étape, nous chargeons le document en utilisant le`Document` et en transmettant le chemin d'accès au fichier DOCX à charger.

## Étape 3 : Configuration des options de sauvegarde OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 Dans cette étape, nous configurons les options de sauvegarde OOXML à l'aide du`OoxmlSaveOptions` classe. Nous fixons le niveau de compression à`SuperFast` pour obtenir une compression plus rapide.

## Étape 4 : Enregistrez le document avec le niveau de compression spécifié

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 Dans cette dernière étape, nous sauvegardons le document en utilisant le`Save` méthode et en passant le chemin d'accès au fichier de sortie avec le`.docx` extension, ainsi que les options de sauvegarde spécifiées.

Vous pouvez désormais exécuter le code source pour définir le niveau de compression lors de l'enregistrement d'un document. Le fichier résultant sera enregistré dans le répertoire spécifié sous le nom "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### Exemple de code source pour définir le niveau de compression à l'aide d'Aspose.Words pour .NET 

```csharp

// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de définition du niveau de compression lors de l'enregistrement d'un document à l'aide d'Aspose.Words pour .NET. En spécifiant le niveau de compression approprié, vous pouvez optimiser la taille du document et la vitesse de génération.

 Le`OoxmlSaveOptions`La classe offre la flexibilité de contrôler le niveau de compression en définissant le`CompressionLevel` propriété à une valeur appropriée, telle que`SuperFast`. Cela vous permet de trouver le bon équilibre entre la taille du fichier et la vitesse de sauvegarde en fonction de vos besoins spécifiques.

L'utilisation de la compression peut être bénéfique lorsque vous devez réduire la taille des fichiers générés, en particulier pour les documents volumineux. Cela peut faciliter le stockage, le partage et la transmission de documents.

Aspose.Words for .NET offre une gamme d'options et de fonctionnalités puissantes pour la manipulation de documents. En utilisant les options de sauvegarde appropriées, vous pouvez personnaliser le processus de génération de documents et optimiser les performances de votre application.

N'hésitez pas à explorer davantage de fonctionnalités d'Aspose.Words for .NET pour améliorer votre flux de travail de génération de documents.
