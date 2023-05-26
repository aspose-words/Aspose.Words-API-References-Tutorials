---
title: Comportement de style intelligent
linktitle: Comportement de style intelligent
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à conserver un comportement de style intelligent lors de la jointure et de l'ajout de documents Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/join-and-append-documents/smart-style-behavior/
---

Ce didacticiel vous guidera tout au long du processus d'utilisation de la fonctionnalité Smart Style Behavior d'Aspose.Words pour .NET. Cette fonctionnalité vous permet de joindre et d'ajouter des documents Word tout en conservant un comportement de style intelligent.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Aspose.Words pour .NET installé. Vous pouvez le télécharger depuis le site Web d'Aspose ou l'installer via NuGet.
2. Visual Studio ou tout autre environnement de développement C#.

## Étape 1 : Initialiser les répertoires de documents

 Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Modifier la valeur de la`dataDir` variable au chemin où se trouvent vos documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez les documents source et de destination

 Ensuite, vous devez charger les documents source et de destination à l'aide de Aspose.Words`Document` classe. Mettez à jour les noms de fichiers dans le`Document` constructeur en fonction des noms de vos documents.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Étape 3 : Insérer un saut de page dans le document de destination

 Pour vous assurer que le contenu ajouté apparaît sur une nouvelle page du document de destination, vous pouvez insérer un saut de page à l'aide d'un`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Étape 4 : Définir les options de comportement du style intelligent

Pour activer le comportement de style intelligent lors de l'opération d'ajout, vous devez créer une instance de`ImportFormatOptions` et réglez le`SmartStyleBehavior` propriété à`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Étape 5 : Ajouter le document source au document de destination

 Maintenant, vous pouvez ajouter le document source au document de destination en utilisant le`InsertDocument` méthode de la`DocumentBuilder` classe. Utilisez le`ImportFormatMode.UseDestinationStyles` paramètre et passez le`ImportFormatOptions` objet pour conserver un comportement de style intelligent.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Étape 6 : Enregistrez le document final

 Enfin, enregistrez le document fusionné avec la fonction Smart Style Behavior activée à l'aide de la`Save` méthode de la`Document` classe.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Exemple de code source pour Smart Style Behavior utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité "Smart Style Behavior" en C# utilisant Aspose.Words pour .NET :
 
```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

C'est ça! Vous avez implémenté avec succès la fonctionnalité Smart Style Behavior à l'aide de Aspose.Words pour .NET. Le document final contiendra le contenu fusionné avec un comportement de style intelligent conservé.