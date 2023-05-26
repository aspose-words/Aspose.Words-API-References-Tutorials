---
title: Page par page
linktitle: Page par page
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour expliquer le code source C # de la fonctionnalité Aspose.Words page par page pour .NET
type: docs
weight: 10
url: /fr/net/split-document/page-by-page/
---

Dans ce didacticiel, nous vous expliquerons comment diviser un document Word en pages individuelles à l'aide de la fonctionnalité Page par page d'Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et obtenir des documents distincts pour chaque page.

## Étape 1 : Chargement du document

Pour commencer, spécifiez le répertoire de votre document et chargez le document dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Étape 2 : Divisez le document par page

Nous allons maintenant parcourir chaque page du document et diviser le document en pages individuelles. Voici comment:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Enregistrez chaque page dans un document distinct.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

## Étape 3 : fusionner des documents

Une fois que vous avez des documents séparés pour chaque page, vous pouvez les fusionner si nécessaire. Voici comment:

```csharp
MergeDocuments();
```

### Exemple de code source pour Page By Page utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Page par page d'Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	int pageCount = doc.PageCount;

	for (int page = 0; page < pageCount; page++)
	{
		// Enregistrez chaque page dans un document distinct.
		Document extractedPage = doc.ExtractPages(page, 1);
		extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
	}
	

	MergeDocuments();

```

Avec ce code, vous pourrez diviser un document Word en pages individuelles en utilisant Aspose.Words pour .NET. Vous pouvez également fusionner des documents distincts si nécessaire.

