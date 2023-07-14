---
title: Supprimer les propriétés de document personnalisées
linktitle: Supprimer les propriétés de document personnalisées
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour supprimer les propriétés personnalisées d'un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-properties/remove-custom-document-properties/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour supprimer les propriétés personnalisées d'un document avec Aspose.Words pour .NET. Cette fonctionnalité vous permet de supprimer une propriété personnalisée spécifique d'un document.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous allons charger le document Word dont nous voulons supprimer les propriétés personnalisées. Utilisez le code suivant pour charger le document :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel du répertoire où se trouve votre document.

## Étape 3 : Supprimer les propriétés personnalisées

Supprimons maintenant une propriété personnalisée spécifique du document. Utilisez le code suivant :

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Ce code supprime la propriété personnalisée "Date autorisée" du document. Vous pouvez remplacer "Date autorisée" par le nom de la propriété personnalisée que vous souhaitez supprimer.

### Exemple de code source pour supprimer les propriétés de document personnalisées à l'aide de Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Assurez-vous de spécifier le bon chemin d'accès au document dans le`dataDir` variable.

Vous avez maintenant appris à supprimer les propriétés personnalisées d'un document à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement supprimer les propriétés personnalisées de vos propres documents.