---
title: Mise en page différente
linktitle: Mise en page différente
second_title: API de traitement de documents Aspose.Words
description: Apprenez à ajouter un document avec différents paramètres de mise en page à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/different-page-setup/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour ajouter un document avec différents paramètres de mise en page à un autre document. Le code source fourni montre comment configurer différents paramètres de page pour les documents source et de destination et assurer une continuité et une numérotation appropriées.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des prérequis suivants :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger depuis[Aspose.Releases]https://releases.aspose.com/words/net/ ou utilisez le gestionnaire de packages NuGet pour l'installer.
- Un chemin d'accès au répertoire de documents où se trouvent les documents source et de destination.

## Étape 2 : Ouvrez les documents source et destination

 Ouvrez les documents source et destination à l'aide de la`Document` constructeur de classe. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : Configurer les paramètres de page pour le document source

Ajustez les paramètres de mise en page du document source pour assurer une suite et une numérotation correctes. Dans cet exemple, nous définissons le début de la section sur`SectionStart.Continuous` et recommencer la numérotation des pages. Nous nous assurons également que la largeur, la hauteur et l'orientation de la page correspondent à la dernière section du document de destination.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Étape 4 : Modifier la mise en forme des paragraphes

 Pour conserver une mise en forme appropriée, parcourez tous les paragraphes du document source et définissez le`KeepWithNext` propriété à`true`. Cela garantit que les paragraphes restent ensemble pendant le processus d'ajout.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Étape 5 : Ajouter le document source au document de destination

 Utilisez le`AppendDocument` méthode du document de destination pour ajouter le document source modifié au document de destination, en préservant la mise en forme source.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 6 : Enregistrer le document de destination

 Enfin, enregistrez le document de destination modifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Ceci termine la mise en œuvre de l'ajout d'un document avec différents paramètres de mise en page à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Different Page Setup utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Définissez le document source pour continuer juste après la fin du document de destination.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Recommencer la numérotation des pages au début du document source.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Pour vous assurer que cela ne se produit pas lorsque le document source a des paramètres de mise en page différents, assurez-vous que
	// les paramètres sont identiques entre la dernière section du document de destination.
	// S'il y a d'autres sections continues qui suivent dans le document source,
	// ceci devra être répété pour ces sections.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Parcourez toutes les sections du document source.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```