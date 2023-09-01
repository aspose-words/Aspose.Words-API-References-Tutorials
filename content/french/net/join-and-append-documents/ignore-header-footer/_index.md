---
title: Ignorer l'en-tête et le pied de page
linktitle: Ignorer l'en-tête et le pied de page
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter un document tout en ignorant le contenu de l'en-tête et du pied de page à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/ignore-header-footer/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour ajouter un document tout en ignorant le contenu de l'en-tête et du pied de page. Le code source fourni montre comment configurer les options de format d'importation pour exclure l'en-tête et le pied de page pendant le processus d'ajout.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des conditions préalables suivantes :

-  Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger depuis[Aspose.Releases]https://releases.aspose.com/words/net/ ou utilisez le gestionnaire de packages NuGet pour l'installer.
- Un chemin de répertoire de documents où se trouvent les documents source et de destination.

## Étape 2 : Ouvrir les documents source et destination

 Ouvrez les documents source et destination à l'aide du`Document` constructeur de classe. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : Configurer les options de format d'importation

 Créez une instance du`ImportFormatOptions` classe et définir le`IgnoreHeaderFooter` propriété à`false`. Cela garantit que le contenu de l’en-tête et du pied de page est inclus lors du processus d’ajout.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Étape 4 : Ajouter le document source au document de destination

 Utilisez le`AppendDocument` méthode du document de destination pour ajouter le document source. Passer`ImportFormatMode.KeepSourceFormatting` comme deuxième paramètre et les options de format d'importation comme troisième paramètre.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Étape 5 : Enregistrez le document de destination

 Enfin, enregistrez le document de destination modifié à l'aide du`Save` méthode du`Document` objet.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Ceci termine la mise en œuvre de l’ajout d’un document tout en ignorant le contenu de l’en-tête et du pied de page à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour ignorer le pied de page de l'en-tête à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```