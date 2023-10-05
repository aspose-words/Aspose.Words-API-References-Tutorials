---
title: Rejoindre en continu
linktitle: Rejoindre en continu
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment joindre deux documents en continu tout en préservant le formatage à l'aide d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/join-continuous/
---

Ce didacticiel explique comment joindre deux documents en continu à l'aide d'Aspose.Words for .NET. Le code source fourni montre comment ajouter un document à la fin d'un autre document tout en conservant le formatage d'origine.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des conditions préalables suivantes :

-  Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger depuis[Aspose.Releases]https://releases.aspose.com/words/net/ ou utilisez le gestionnaire de packages NuGet pour l'installer.
- Un chemin de répertoire de documents où se trouvent les documents source et de destination.

## Étape 2 : Ouvrir les documents source et destination

 Ouvrez les documents source et destination à l'aide du`Document` constructeur de classe. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : Configurer le début de section continu

 Pour que le document source apparaisse juste après le contenu du document de destination, définissez le`SectionStart` propriété de la première section du document source à`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Étape 4 : Joindre le document source

 Ajoutez le document source au document de destination à l'aide du`AppendDocument` méthode du`Document` classe. Définissez le mode de format d'importation sur`ImportFormatMode.KeepSourceFormatting` pour conserver les styles originaux du document source.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 5 : Enregistrez le document modifié

 Enfin, enregistrez le document de destination modifié à l'aide du`Save` méthode du`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Ceci termine la mise en œuvre de la jonction continue de deux documents à l’aide d’Aspose.Words for .NET.

### Exemple de code source pour Join Continuous à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Faites apparaître le document juste après le contenu du document de destination.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Ajoutez le document source en utilisant les styles d'origine trouvés dans le document source.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```