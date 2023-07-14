---
title: Rejoindre une nouvelle page
linktitle: Rejoindre une nouvelle page
second_title: API de traitement de documents Aspose.Words
description: Apprenez à joindre deux documents sur une nouvelle page tout en préservant la mise en forme à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/join-new-page/
---

Ce tutoriel explique comment joindre deux documents sur une nouvelle page en utilisant Aspose.Words pour .NET. Le code source fourni montre comment ajouter un document à la fin d'un autre document tout en commençant le document ajouté sur une nouvelle page.

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

## Étape 3 : Configurer le début de la nouvelle section de la page

 Pour commencer le document ajouté sur une nouvelle page, définissez le`SectionStart` propriété de la première section du document source pour`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Étape 4 : Ajouter le document source

 Ajoutez le document source au document de destination à l'aide de la`AppendDocument` méthode de la`Document` classe. Définissez le mode de format d'importation sur`ImportFormatMode.KeepSourceFormatting` pour conserver les styles d'origine du document source.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 5 : Enregistrez le document modifié

 Enfin, enregistrez le document de destination modifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Ceci termine l'implémentation de la jointure de deux documents sur une nouvelle page à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Join New Page en utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Définissez le document ajouté pour commencer sur une nouvelle page.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Ajoutez le document source en utilisant les styles d'origine trouvés dans le document source.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```