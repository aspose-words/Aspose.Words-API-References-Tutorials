---
title: Conserver la numérotation des sources
linktitle: Conserver la numérotation des sources
second_title: API de traitement de documents Aspose.Words
description: Apprenez à ajouter un document tout en préservant la mise en forme de la numérotation source dans Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/keep-source-numbering/
---

Ce didacticiel explique comment ajouter un document source à un document de destination tout en préservant la mise en forme de numérotation d'origine des paragraphes numérotés à l'aide de Aspose.Words pour .NET.

## Étape 1 : Configurer le projet

Assurez-vous d'avoir les prérequis suivants :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger depuis[Aspose.Releases]https://releases.aspose.com/words/net/ ou utilisez le gestionnaire de packages NuGet pour l'installer.
- Un chemin d'accès au répertoire de documents où les documents source et de destination seront enregistrés.

## Étape 2 : Créer les documents de destination et source

 Créer des instances de`Document` pour les documents de destination et source.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : conserver la numérotation des sources lors de l'importation

 Pour conserver la mise en forme de la numérotation des paragraphes numérotés du document source, créez une instance de`ImportFormatOptions` Et mettre`KeepSourceNumbering` pour`true` . Utiliser un`NodeImporter` pour importer des nœuds du document source vers le document de destination, en spécifiant`ImportFormatMode.KeepSourceFormatting` et le`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Étape 4 : Importer et ajouter des paragraphes

 Parcourez les paragraphes du document source et importez chaque paragraphe dans le document de destination à l'aide de la`importer`. Ajoutez les nœuds importés au corps du document de destination.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Étape 5 : Enregistrez le document modifié

 Enregistrez le document modifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Ceci termine la mise en œuvre de l'ajout d'un document source à un document de destination tout en conservant la mise en forme de numérotation d'origine à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Keep Source Numbering en utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Conservez le formatage de la liste source lors de l'importation de paragraphes numérotés.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```