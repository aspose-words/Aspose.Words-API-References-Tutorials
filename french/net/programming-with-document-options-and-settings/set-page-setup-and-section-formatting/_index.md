---
title: Définir la mise en page et le formatage des sections
linktitle: Définir la mise en page et le formatage des sections
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour configurer la mise en page et la mise en forme des sections d'un document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

Dans ce didacticiel, nous vous guiderons à travers le code source C # pour configurer la disposition et le formatage des sections avec Aspose.Words pour .NET. Cette fonction vous permet de définir l'orientation de la page, les marges et le format du papier.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous que la bibliothèque Aspose.Words pour .NET est référencée dans votre projet.

## Étape 2 : Création du document

Dans cette étape, nous allons créer un nouveau document. Utilisez le code suivant pour créer le document et initialiser le constructeur :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin d'accès réel du répertoire où vous souhaitez enregistrer le document.

## Étape 3 : Configurer la mise en page et enregistrer le document

Configurons maintenant la mise en page du document. Utilisez le code suivant pour définir l'orientation, les marges et la taille du papier :

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Ce code définira l'orientation de la page sur paysage, la marge de gauche sur 50 et la taille du papier sur 10x14.

### Exemple de code source pour définir la mise en page et le formatage des sections à l'aide de Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

Assurez-vous de spécifier le chemin d'accès correct au répertoire dans lequel vous souhaitez enregistrer le document dans le`dataDir` variable.

Vous avez maintenant appris à configurer la mise en page et la mise en forme des sections d'un document à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez facilement personnaliser la mise en page et la mise en forme de vos propres documents.