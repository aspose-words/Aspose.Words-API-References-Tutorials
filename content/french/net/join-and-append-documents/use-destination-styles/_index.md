---
title: Utiliser les styles de destination
linktitle: Utiliser les styles de destination
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment joindre et ajouter des documents Word tout en appliquant des styles de document de destination à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/use-destination-styles/
---

Ce didacticiel vous guidera tout au long du processus d'utilisation de la fonctionnalité Utiliser les styles de destination d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de joindre et d'ajouter des documents Word tout en appliquant les styles du document de destination.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Aspose.Words pour .NET installé. Vous pouvez le télécharger depuis le site Web Aspose ou l'installer via NuGet.
2. Visual Studio ou tout autre environnement de développement C#.

## Étape 1 : initialiser les répertoires de documents

 Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. Modifier la valeur du`dataDir` variable au chemin où se trouvent vos documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger les documents source et de destination

Ensuite, vous devez charger les documents source et de destination à l'aide du Aspose.Words`Document` classe. Mettez à jour les noms de fichiers dans le`Document` constructeur en fonction des noms de vos documents.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : ajouter le document source avec les styles de destination

 Pour ajouter le document source au document de destination tout en appliquant les styles du document de destination, vous pouvez utiliser l'option`AppendDocument` méthode du`Document` classe avec le`ImportFormatMode.UseDestinationStyles` paramètre.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Étape 4 : Enregistrez le document final

 Enfin, enregistrez le document fusionné avec la fonctionnalité Utiliser les styles de destination activée à l'aide du`Save` méthode du`Document` classe.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Exemple de code source pour utiliser les styles de destination à l'aide d'Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité « Utiliser les styles de destination » en C# à l'aide d'Aspose.Words pour .NET :

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ajoutez le document source en utilisant les styles du document de destination.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

C'est ça! Vous avez implémenté avec succès la fonctionnalité Utiliser les styles de destination à l’aide d’Aspose.Words pour .NET. Le document final contiendra le contenu fusionné avec les styles du document de destination appliqués.