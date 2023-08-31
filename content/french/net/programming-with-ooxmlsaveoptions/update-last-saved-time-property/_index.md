---
title: Mettre à jour la propriété de l'heure du dernier enregistrement
linktitle: Mettre à jour la propriété de l'heure du dernier enregistrement
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment mettre à jour automatiquement la propriété Last Saved Time lors de l'enregistrement d'un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
Dans ce didacticiel, nous allons explorer le code source C # fourni pour mettre à jour la dernière propriété de temps d'enregistrement lors de l'enregistrement d'un document à l'aide de Aspose.Words pour .NET. Cette fonctionnalité vous permet de mettre à jour automatiquement la dernière propriété d'heure de sauvegarde du document généré.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 Dans cette étape, nous configurons les options de sauvegarde OOXML à l'aide de`OoxmlSaveOptions` classe. Nous activons la mise à jour automatique de la dernière propriété d'heure de sauvegarde en définissant`UpdateLastSavedTimeProperty` pour`true`.

## Étape 4 : Enregistrer le document avec la propriété mise à jour

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 Dans cette dernière étape, nous enregistrons le document en utilisant le`Save` méthode et en passant le chemin vers le fichier de sortie avec la`.docx` extension, ainsi que les options d'enregistrement spécifiées.

Vous pouvez maintenant exécuter le code source pour mettre à jour automatiquement la dernière propriété d'heure d'enregistrement lors de l'enregistrement d'un document. Le fichier résultant sera enregistré dans le répertoire spécifié avec le nom "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Exemple de code source pour la propriété Update Last Saved Time à l'aide de Aspose.Words pour .NET 

```csharp

//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de mise à jour automatique de la propriété de l'heure du dernier enregistrement lors de l'enregistrement d'un document à l'aide de Aspose.Words pour .NET. En activant cette fonctionnalité avec les options d'enregistrement OOXML, vous pouvez vous assurer que la dernière propriété d'heure d'enregistrement est mise à jour automatiquement dans le document généré.

La mise à jour de la propriété de l'heure du dernier enregistrement peut être utile pour suivre les modifications et les versions d'un document. Il garde également une trace du dernier enregistrement du document, ce qui peut être utile dans divers scénarios.

Aspose.Words pour .NET facilite la mise à jour automatique de la propriété Heure de la dernière sauvegarde en fournissant des options de sauvegarde flexibles et puissantes. Vous pouvez intégrer cette fonctionnalité dans vos projets pour vous assurer que les documents générés contiennent des informations de sauvegarde précises.