---
title: Ignorer les zones de texte
linktitle: Ignorer les zones de texte
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter un document tout en ignorant le formatage de la zone de texte à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/ignore-text-boxes/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour ajouter un document tout en préservant la mise en forme des zones de texte. Le code source fourni montre comment configurer les options de format d'importation pour inclure des zones de texte pendant le processus d'ajout.

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

## Étape 3 : Configurer les options de format d'importation

 Créez une instance du`ImportFormatOptions` classe et définir le`IgnoreTextBoxes`propriété à`false`. Cela garantit que les zones de texte sont incluses lors du processus d'ajout tout en préservant leur mise en forme.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Étape 4 : Ajouter le contenu de la zone de texte

 Créer un`NodeImporter` objet et utilisez-le pour importer des nœuds de zone de texte du document source vers le document de destination. Parcourez chaque paragraphe du document source et importez-le dans le document de destination.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Étape 5 : Enregistrez le document de destination

 Enfin, enregistrez le document de destination modifié à l'aide du`Save` méthode du`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Ceci termine la mise en œuvre de l’ajout d’un document tout en préservant le formatage de la zone de texte à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour ignorer les zones de texte à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Conservez le formatage des zones de texte source lors de l’importation.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```