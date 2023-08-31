---
title: Définir le niveau de compression
linktitle: Définir le niveau de compression
second_title: API de traitement de documents Aspose.Words
description: Apprenez à définir le niveau de compression lors de l'enregistrement d'un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
Dans ce didacticiel, nous allons explorer le code source C # fourni pour définir le niveau de compression lors de l'enregistrement d'un document à l'aide de Aspose.Words pour .NET. Cette fonctionnalité vous permet de contrôler le niveau de compression du document généré.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words pour .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Chargement du document

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Dans cette étape, nous chargeons le document en utilisant le`Document` méthode et en passant le chemin vers le fichier DOCX à charger.

## Étape 3 : Configuration des options de sauvegarde OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 Dans cette étape, nous configurons les options de sauvegarde OOXML à l'aide de`OoxmlSaveOptions` classe. Nous avons défini le niveau de compression sur`SuperFast` pour obtenir une compression plus rapide.

## Étape 4 : Enregistrez le document avec le niveau de compression spécifié

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 Dans cette dernière étape, nous enregistrons le document en utilisant le`Save` méthode et en passant le chemin vers le fichier de sortie avec la`.docx` extension, ainsi que les options d'enregistrement spécifiées.

Vous pouvez maintenant exécuter le code source pour définir le niveau de compression lors de l'enregistrement d'un document. Le fichier résultant sera enregistré dans le répertoire spécifié sous le nom "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### Exemple de code source pour définir le niveau de compression à l'aide de Aspose.Words pour .NET 

```csharp

//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de définition du niveau de compression lors de l'enregistrement d'un document à l'aide de Aspose.Words pour .NET. En spécifiant le niveau de compression approprié, vous pouvez optimiser la taille du document et la vitesse de génération.

 Le`OoxmlSaveOptions`offre la possibilité de contrôler le niveau de compression en définissant la`CompressionLevel` propriété à une valeur appropriée, telle que`SuperFast`. Cela vous permet de trouver le bon équilibre entre la taille du fichier et la vitesse de sauvegarde en fonction de vos besoins spécifiques.

L'utilisation de la compression peut être bénéfique lorsque vous devez réduire la taille des fichiers générés, en particulier pour les documents volumineux. Cela peut faciliter le stockage, le partage et la transmission de documents.

Aspose.Words pour .NET offre une gamme d'options et de fonctionnalités puissantes pour la manipulation de documents. En utilisant les options de sauvegarde appropriées, vous pouvez personnaliser le processus de génération de documents et optimiser les performances de votre application.

N'hésitez pas à explorer plus de fonctionnalités d'Aspose.Words pour .NET pour améliorer votre flux de travail de génération de documents.
