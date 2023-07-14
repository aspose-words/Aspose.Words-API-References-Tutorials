---
title: Ajouter des propriétés de document personnalisées
linktitle: Ajouter des propriétés de document personnalisées
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour ajouter des propriétés personnalisées à un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-properties/add-custom-document-properties/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour ajouter des propriétés personnalisées à un document avec Aspose.Words pour .NET. Cette fonction vous permet d'ajouter des informations personnalisées au document.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous allons charger le document Word auquel nous voulons ajouter des propriétés personnalisées. Utilisez le code suivant pour charger le document :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel du répertoire où se trouve votre document.

## Étape 3 : Ajoutez des propriétés personnalisées

Ajoutons maintenant des propriétés personnalisées au document. Utilisez le code suivant pour ajouter les propriétés :

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Ce code vérifie d'abord si la propriété "Autorisé" existe déjà dans les propriétés personnalisées. S'il existe, le processus est interrompu. Sinon, les propriétés personnalisées sont ajoutées au document.

### Exemple de code source pour Ajouter des propriétés de document personnalisées à l'aide d'Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Assurez-vous de spécifier le bon chemin d'accès au document dans le`dataDir` variable.

Vous avez maintenant appris à ajouter des propriétés personnalisées à un document à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement ajouter vos propres propriétés personnalisées à vos documents.