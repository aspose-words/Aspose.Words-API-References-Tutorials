---
title: Insérer un document avec le constructeur
linktitle: Insérer un document avec le constructeur
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer un document à la fin d'un autre document en utilisant Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/insert-document-with-builder/
---

 Ce tutoriel explique comment utiliser Aspose.Words pour .NET pour insérer un document dans un autre document en utilisant le`DocumentBuilder` classe. Le code source fourni montre comment insérer un document à la fin d'un autre document tout en préservant la mise en forme source.

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

## Étape 3 : Initialiser le DocumentBuilder

 Créez une nouvelle instance de`DocumentBuilder` classe et passez le document de destination en paramètre.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Étape 4 : positionner le DocumentBuilder

 Bouge le`DocumentBuilder` à la fin du document à l'aide de la`MoveToDocumentEnd` méthode. Insérez un saut de page pour séparer le contenu existant du document inséré.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Étape 5 : Insérez le document source

 Utilisez le`InsertDocument` méthode de la`DocumentBuilder` classe pour insérer le document source dans le document de destination. Définissez le mode de format d'importation sur`ImportFormatMode.KeepSourceFormatting` pour conserver la mise en forme de la source.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Étape 6 : Enregistrez le document modifié

 Enfin, enregistrez le document de destination modifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Ceci termine l'implémentation de l'insertion d'un document dans un autre document à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Insérer un document avec Builder en utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```