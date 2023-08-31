---
title: Exporter les signets de pied de page d’en-tête de document Word vers un document PDF
linktitle: Exporter les signets de pied de page d’en-tête de document Word vers un document PDF
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour exporter les signets d’en-tête de document Word vers les signets de document PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Cet article fournit un guide étape par étape sur la façon d'exporter les signets d'en-tête et de pied de page d'un document Word vers la fonctionnalité de document PDF avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. A la fin de ce tutoriel, vous serez en mesure de comprendre comment exporter des signets à partir des en-têtes et pieds de page d'un document et générer un PDF avec les signets appropriés.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words for .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin d’accès au répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle « Signets dans les en-têtes et les pieds de page.docx » et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Étape 3 : Configurer les options d'enregistrement au format PDF

 Pour exporter les signets d'en-tête et de pied de page, nous devons configurer le`PdfSaveOptions` objet. Dans cet exemple, nous définissons le niveau de présentation des favoris par défaut sur 1 et le mode d'exportation des favoris d'en-tête et de pied de page sur « Premier ».

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Étape 4 : Enregistrez le document au format PDF avec des signets d'en-tête et de pied de page

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options de sauvegarde configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

C'est tout ! Vous avez exporté avec succès les signets d'en-tête et de pied de page d'un document et généré un PDF avec les signets appropriés à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour exporter des signets d’en-tête et de pied de page avec Aspose.Words for .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment exporter des signets d'en-tête et de pied de page d'un document Word vers un document PDF à l'aide d'Aspose.Words pour .NET. Les signets exportés permettent une navigation facile et une référence rapide aux en-têtes et pieds de page correspondants dans le document PDF généré. Suivez les étapes décrites pour exporter les signets d'en-tête et de pied de page d'un document et générer un PDF avec les signets appropriés à l'aide d'Aspose.Words for .NET. Assurez-vous de spécifier le chemin d'accès correct à vos documents et de configurer les options d'enregistrement selon vos besoins.

### Questions fréquemment posées

### Q : Qu'est-ce que l'exportation de signets d'en-tête et de pied de page d'un document Word vers un document PDF ?
R : L'exportation de signets d'en-tête et de pied de page d'un document Word vers un document PDF est une fonctionnalité permettant de conserver et de générer des signets dans le document PDF à partir des en-têtes et des pieds de page. pieds de page du document Word original. Cela permet aux utilisateurs de naviguer rapidement et facilement dans le document PDF en utilisant des signets correspondant aux en-têtes et pieds de page.

### Q : Comment puis-je utiliser Aspose.Words for .NET pour exporter les signets d'en-tête et de pied de page d'un document Word vers un document PDF ?
R : Pour exporter les signets d'en-tête et de pied de page d'un document Word vers un document PDF à l'aide d'Aspose.Words for .NET, procédez comme suit :

 Définissez le chemin du répertoire où se trouvent vos documents en remplaçant`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel de votre répertoire de documents.

 Chargez le document que vous souhaitez traiter à l'aide du`Document` classe et spécifiez le chemin d’accès au document Word dans le répertoire de documents spécifié.

 Configurez les options d'enregistrement au format PDF en créant une instance du`PdfSaveOptions` classe et en définissant les options de signets d’en-tête et de pied de page appropriées.

 Enregistrez le document au format PDF à l'aide du`Save` méthode du`Document`classe spécifiant le chemin et les options de sauvegarde.

### Q : Quels sont les avantages de l’exportation des signets d’en-tête et de pied de page vers un document PDF ?
R : Les avantages de l’exportation des signets d’en-tête et de pied de page dans un document PDF sont :

Navigation facile : les signets permettent aux utilisateurs de naviguer facilement dans un document PDF en se référant à des en-têtes et des pieds de page spécifiques.

Référence rapide : les signets permettent aux utilisateurs de trouver rapidement les sections pertinentes du document PDF en fonction des en-têtes et des pieds de page.