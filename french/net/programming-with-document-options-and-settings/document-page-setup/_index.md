---
title: Mise en page du document
linktitle: Mise en page du document
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour configurer une mise en page de document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-options-and-settings/document-page-setup/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C # pour configurer la mise en page du document avec Aspose.Words pour .NET. Cette fonction vous permet de définir le mode de mise en page, le nombre de caractères par ligne et le nombre de lignes par page.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Chargement du document

Dans cette étape, nous allons charger le document Word que nous voulons configurer. Utilisez le code suivant pour charger le document :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel du répertoire où se trouve votre document.

## Étape 3 : Configurer la mise en page

Configurons maintenant la mise en page du document. Utilisez le code suivant pour définir le mode de mise en page, le nombre de caractères par ligne et le nombre de lignes par page :

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Ce code définit le mode de mise en page sur "Grille", puis spécifie le nombre de caractères par ligne et le nombre de lignes par page.

### Exemple de code source pour la mise en page du document à l'aide de Aspose.Words pour .NET


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Définissez le mode de mise en page d'une section permettant de définir le comportement de la grille du document.
	// Notez que l'onglet Grille de document devient visible dans la boîte de dialogue Mise en page de MS Word
	// si une langue asiatique est définie comme langue d'édition.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Assurez-vous de spécifier le bon chemin d'accès au document dans le`dataDir` variable.

Vous avez maintenant appris à configurer la mise en page d'un document à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement personnaliser la mise en page de vos propres documents.