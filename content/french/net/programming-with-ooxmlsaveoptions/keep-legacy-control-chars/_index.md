---
title: Conserver les caractères de contrôle hérités
linktitle: Conserver les caractères de contrôle hérités
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment conserver les caractères de contrôle hérités lors de l’enregistrement d’un document avec Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

Dans ce didacticiel, nous explorerons le code source C# fourni pour conserver les caractères de contrôle hérités lors de l'enregistrement d'un document à l'aide d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de conserver les caractères de contrôle spéciaux lors de la conversion ou de l'enregistrement d'un document.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words for .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Chargement du document

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 Dans cette étape, nous chargeons le document en utilisant le`Document` et en transmettant le chemin d'accès au fichier contenant les caractères de contrôle hérités.

## Étape 3 : Configuration des options de sauvegarde OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

Dans cette étape, nous configurons les options de sauvegarde OOXML en créant un nouveau`OoxmlSaveOptions`objet. Nous précisons le format de sauvegarde souhaité (ici,`FlatOpc` ) et activez le`KeepLegacyControlChars` option pour conserver les caractères de contrôle hérités.

## Étape 4 : Enregistrement du document avec les caractères de contrôle hérités

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 Dans cette dernière étape, nous sauvegardons le document en utilisant le`Save` méthode et en passant le chemin d'accès au fichier de sortie avec le`.docx` extension, ainsi que les options de sauvegarde spécifiées.

Vous pouvez désormais exécuter du code source pour conserver les caractères de contrôle hérités lors de l'enregistrement d'un document. Le fichier résultant sera enregistré dans le répertoire spécifié sous le nom "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Exemple de code source pour conserver les caractères de contrôle hérités à l'aide d'Aspose.Words pour .NET 
```csharp

//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de préservation des caractères de contrôle hérités lors de l'enregistrement d'un document à l'aide d'Aspose.Words pour .NET. Nous avons appris à conserver les caractères spéciaux qui peuvent être importants pour le formatage ou l'affichage correct du document.

 La préservation des caractères de contrôle hérités est particulièrement utile lors du traitement de texte avec des documents qui utilisent des fonctionnalités plus anciennes ou spécifiques, telles que des caractères de contrôle spéciaux. En activant le`KeepLegacyControlChars`lors de l’enregistrement du document, vous vous assurez que ces caractères sont conservés.

Aspose.Words for .NET offre une gamme d'options de sauvegarde flexibles et puissantes pour répondre à vos besoins de manipulation de documents. En utilisant les options appropriées, vous pouvez personnaliser le processus de sauvegarde pour préserver les caractéristiques spécifiques de vos documents.

N'hésitez pas à intégrer cette fonctionnalité dans vos projets Aspose.Words for .NET pour garantir l'intégrité et la préservation des caractères de contrôle hérités dans vos documents.