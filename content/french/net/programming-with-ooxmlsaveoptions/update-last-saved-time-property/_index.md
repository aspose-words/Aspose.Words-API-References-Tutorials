---
title: Propriété Mettre à jour la dernière heure enregistrée
linktitle: Propriété Mettre à jour la dernière heure enregistrée
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment mettre à jour automatiquement la propriété Dernière heure enregistrée lors de l’enregistrement d’un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
Dans ce didacticiel, nous explorerons le code source C# fourni pour mettre à jour la dernière propriété d'heure de sauvegarde lors de l'enregistrement d'un document à l'aide d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de mettre à jour automatiquement la propriété de dernière heure de sauvegarde du document généré.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 Dans cette étape, nous configurons les options de sauvegarde OOXML à l'aide du`OoxmlSaveOptions` classe. Nous activons la mise à jour automatique de la dernière propriété d'heure de sauvegarde en définissant`UpdateLastSavedTimeProperty` à`true`.

## Étape 4 : Enregistrez le document avec la propriété mise à jour

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 Dans cette dernière étape, nous sauvegardons le document en utilisant le`Save` méthode et en passant le chemin d'accès au fichier de sortie avec le`.docx` extension, ainsi que les options de sauvegarde spécifiées.

Vous pouvez désormais exécuter le code source pour mettre à jour automatiquement la dernière propriété d'heure de sauvegarde lors de l'enregistrement d'un document. Le fichier résultant sera enregistré dans le répertoire spécifié sous le nom "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Exemple de code source pour la propriété Mettre à jour la dernière heure enregistrée à l’aide d’Aspose.Words pour .NET 

```csharp

//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de mise à jour automatique de la dernière propriété d'heure de sauvegarde lors de l'enregistrement d'un document à l'aide d'Aspose.Words pour .NET. En activant cette fonctionnalité avec les options de sauvegarde OOXML, vous pouvez vous assurer que la dernière propriété d'heure de sauvegarde est automatiquement mise à jour dans le document généré.

La mise à jour de la dernière propriété d'heure de sauvegarde peut être utile pour suivre les modifications et les versions d'un document. Il garde également une trace de la dernière fois que le document a été enregistré, ce qui peut être utile dans divers scénarios.

Aspose.Words for .NET facilite la mise à jour automatique de la propriété Last Backup Time en fournissant des options de sauvegarde flexibles et puissantes. Vous pouvez intégrer cette fonctionnalité dans vos projets pour garantir que les documents générés contiennent des informations de sauvegarde précises.