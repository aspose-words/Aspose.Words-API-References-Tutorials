---
title: Rejoindre en continu
linktitle: Rejoindre en continu
second_title: API de traitement de documents Aspose.Words
description: Apprenez à joindre deux documents en continu tout en préservant la mise en forme à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/join-continuous/
---

Ce tutoriel explique comment joindre deux documents en continu en utilisant Aspose.Words pour .NET. Le code source fourni montre comment ajouter un document à la fin d'un autre document tout en conservant la mise en forme d'origine.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des prérequis suivants :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser le gestionnaire de packages NuGet pour l'installer.
- Un chemin d'accès au répertoire de documents où se trouvent les documents source et de destination.

## Étape 2 : Ouvrez les documents source et destination

 Ouvrez les documents source et destination à l'aide de la`Document` constructeur de classe. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : Configurer le démarrage de la section en continu

 Pour faire apparaître le document source juste après le contenu du document de destination, définissez le`SectionStart` propriété de la première section du document source pour`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Étape 4 : Ajouter le document source

 Ajoutez le document source au document de destination à l'aide de la`AppendDocument` méthode de la`Document` classe. Définissez le mode de format d'importation sur`ImportFormatMode.KeepSourceFormatting` pour conserver les styles d'origine du document source.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 5 : Enregistrez le document modifié

 Enfin, enregistrez le document de destination modifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Ceci termine la mise en œuvre de la jointure de deux documents en continu à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Join Continuous en utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Faites apparaître le document juste après le contenu du document de destination.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Ajoutez le document source en utilisant les styles d'origine trouvés dans le document source.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```