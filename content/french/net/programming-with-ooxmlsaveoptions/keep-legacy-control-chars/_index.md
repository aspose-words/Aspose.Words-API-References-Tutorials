---
title: Conserver les anciens caractères de contrôle
linktitle: Conserver les anciens caractères de contrôle
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment conserver les caractères de contrôle hérités lors de l'enregistrement d'un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

Dans ce didacticiel, nous allons explorer le code source C # fourni pour conserver les caractères de contrôle hérités lors de l'enregistrement d'un document à l'aide de Aspose.Words pour .NET. Cette fonction vous permet de conserver les caractères de contrôle spéciaux lors de la conversion ou de l'enregistrement d'un document.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement avec Aspose.Words pour .NET. Assurez-vous d'avoir ajouté les références nécessaires et importé les espaces de noms appropriés.

## Étape 2 : Chargement du document

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 Dans cette étape, nous chargeons le document en utilisant le`Document` méthode et en transmettant le chemin d'accès au fichier contenant les caractères de contrôle hérités.

## Étape 3 : Configuration des options de sauvegarde OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

Dans cette étape, nous configurons les options de sauvegarde OOXML en créant un nouveau`OoxmlSaveOptions`objet. Nous spécifions le format de sauvegarde souhaité (ici,`FlatOpc` ) et activez le`KeepLegacyControlChars` option pour conserver les caractères de contrôle hérités.

## Étape 4 : Enregistrer le document avec des caractères de contrôle hérités

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 Dans cette dernière étape, nous enregistrons le document en utilisant le`Save` méthode et en passant le chemin vers le fichier de sortie avec la`.docx` extension, ainsi que les options d'enregistrement spécifiées.

Vous pouvez maintenant exécuter le code source pour conserver les caractères de contrôle hérités lors de l'enregistrement d'un document. Le fichier résultant sera enregistré dans le répertoire spécifié sous le nom "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Exemple de code source pour Keep Legacy Control Chars en utilisant Aspose.Words pour .NET 
```csharp

//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Conclusion

Dans ce didacticiel, nous avons exploré la fonctionnalité de préservation des caractères de contrôle hérités lors de l'enregistrement d'un document à l'aide de Aspose.Words pour .NET. Nous avons appris à conserver les caractères spéciaux qui peuvent être importants pour un formatage ou un affichage correct du document.

 La conservation des caractères de contrôle hérités est particulièrement utile lors du traitement de texte avec des documents qui utilisent des fonctionnalités plus anciennes ou spécifiques, telles que des caractères de contrôle spéciaux. En activant le`KeepLegacyControlChars`lors de l'enregistrement du document, vous vous assurez que ces caractères sont conservés.

Aspose.Words pour .NET offre une gamme d'options de sauvegarde flexibles et puissantes pour répondre à vos besoins de manipulation de documents. En utilisant les options appropriées, vous pouvez personnaliser le processus de sauvegarde pour conserver les caractéristiques spécifiques de vos documents.

N'hésitez pas à intégrer cette fonctionnalité dans vos projets Aspose.Words pour .NET afin d'assurer l'intégrité et la préservation des caractères de contrôle hérités dans vos documents.