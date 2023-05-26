---
title: Exporter les signets d'en-tête de pied de page
linktitle: Exporter les signets d'en-tête de pied de page
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour exporter des signets d'en-tête et de pied de page avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Cet article fournit un guide étape par étape sur l'utilisation de la fonctionnalité Exporter les signets d'en-tête et de pied de page avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment exporter des signets à partir des en-têtes et des pieds de page d'un document et générer un PDF avec les signets appropriés.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin vers le répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle "Signets dans les en-têtes et les pieds de page.docx" et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Étape 3 : Configurer les options d'enregistrement au format PDF

 Pour exporter les signets d'en-tête et de pied de page, nous devons configurer le`PdfSaveOptions` objet. Dans cet exemple, nous définissons le niveau de contour des signets par défaut sur 1 et le mode d'exportation des signets d'en-tête et de pied de page sur "Premier".

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Étape 4 : Enregistrez le document au format PDF avec les en-têtes et les pieds de page des signets

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options d'enregistrement configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

C'est tout ! Vous avez réussi à exporter des signets d'en-tête et de pied de page à partir d'un document et à générer un PDF avec les signets appropriés à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour exporter des signets d'en-tête et de pied de page avec Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```
