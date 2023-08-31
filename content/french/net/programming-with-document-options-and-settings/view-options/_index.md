---
title: Options d'affichage
linktitle: Options d'affichage
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour configurer les options d'affichage des documents avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-options-and-settings/view-options/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C# pour configurer les options d'affichage avec Aspose.Words pour .NET. Cette fonction vous permet de personnaliser le mode d'affichage et le niveau de zoom dans un document.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous allons charger le document Word pour lequel nous voulons configurer les options d'affichage. Utilisez le code suivant pour charger le document :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel du répertoire où se trouve votre document.

## Étape 3 : Configurer les options d'affichage

Nous allons maintenant configurer les options d'affichage du document. Utilisez le code suivant pour définir le mode d'affichage et le niveau de zoom :

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Ce code définit le mode d'affichage sur "PageLayout" et le niveau de zoom sur 50 %.

### Exemple de code source pour les options d'affichage à l'aide de Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Assurez-vous de spécifier le bon chemin d'accès au document dans le`dataDir` variable.

Vous avez maintenant appris à configurer les options d'affichage des documents à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement personnaliser l'affichage de vos propres documents.