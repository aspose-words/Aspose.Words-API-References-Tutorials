---
title: Insérer un document avec le générateur
linktitle: Insérer un document avec le générateur
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un document à la fin d'un autre document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/insert-document-with-builder/
---

 Ce didacticiel explique comment utiliser Aspose.Words for .NET pour insérer un document dans un autre document à l'aide de l'outil`DocumentBuilder` classe. Le code source fourni montre comment insérer un document à la fin d'un autre document tout en préservant le formatage source.

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

## Étape 3 : initialiser DocumentBuilder

 Créez une nouvelle instance du`DocumentBuilder` classe et transmettez le document de destination en paramètre.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Étape 4 : Positionner le DocumentBuilder

 Bouge le`DocumentBuilder` à la fin du document en utilisant le`MoveToDocumentEnd` méthode. Insérez un saut de page pour séparer le contenu existant du document inséré.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Étape 5 : Insérez le document source

 Utilisez le`InsertDocument` méthode du`DocumentBuilder` classe pour insérer le document source dans le document de destination. Définissez le mode de format d'importation sur`ImportFormatMode.KeepSourceFormatting` pour conserver le formatage source.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 6 : Enregistrez le document modifié

 Enfin, enregistrez le document de destination modifié à l'aide du`Save` méthode du`Document` objet.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Ceci termine l’implémentation de l’insertion d’un document dans un autre document à l’aide d’Aspose.Words for .NET.

### Exemple de code source pour Insérer un document avec Builder à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```