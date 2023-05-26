---
title: Enregistrement d'images au format WMF
linktitle: Enregistrement d'images au format WMF
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à enregistrer des images au format WMF lors de la conversion au format RTF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-rtfsaveoptions/saving-images-as-wmf/
---

Dans ce didacticiel, nous allons explorer le code source C# fourni pour la fonctionnalité "Enregistrement d'images au format WMF avec options d'enregistrement RTF" avec Aspose.Words pour .NET. Cette fonction vous permet d'enregistrer des images de document au format Windows Metafile (WMF) lors de la conversion au format RTF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words pour .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Chargement du document

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Dans cette étape, nous chargeons le document en utilisant le`Document` méthode et en passant le chemin vers le fichier DOCX à charger.

## Étape 3 : Configuration des options de sauvegarde

```csharp
RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };
```

Dans cette étape, nous configurons les options de sauvegarde RTF. Nous créons un nouveau`RtfSaveOptions` objet et définissez le`SaveImagesAsWmf` propriété à`true`. Cela indique à Aspose.Words d'enregistrer les images du document au format WMF lors de la conversion en RTF.

## Étape 4 : Enregistrer le document

```csharp
doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```

 Dans cette dernière étape, nous enregistrons le document résultant au format RTF en utilisant le`Save` et en transmettant le chemin d'accès au fichier de sortie, ainsi que les options d'enregistrement spécifiées.

Vous pouvez maintenant exécuter le code source pour enregistrer les images de document au format WMF lors de la conversion au format RTF. Le document résultant sera enregistré dans le répertoire spécifié avec le nom "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf".

### Exemple de code source pour la fonctionnalité d'enregistrement d'images WMF avec des options d'enregistrement RTF avec Aspose.Words pour .NET".

```csharp

            
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");

RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };

doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
            
        
```
## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité d'enregistrement d'images au format WMF avec les options d'enregistrement RTF dans Aspose.Words pour .NET. Nous avons appris à enregistrer les images d'un document au format WMF lors de la conversion au format RTF.

Cette fonctionnalité est utile lorsque vous souhaitez conserver la qualité et la résolution des images dans vos documents RTF. En enregistrant les images au format WMF, vous pouvez vous assurer que leur apparence et leur netteté restent intactes.

Aspose.Words pour .NET offre de nombreuses fonctionnalités avancées pour la manipulation et la génération de documents. L'enregistrement d'images au format WMF lors de la conversion au format RTF est l'un des nombreux outils puissants qu'il vous offre.