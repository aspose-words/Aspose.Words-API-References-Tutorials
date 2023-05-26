---
title: Afficher le titre du document dans la barre de titre de la fenêtre
linktitle: Afficher le titre du document dans la barre de titre de la fenêtre
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à afficher le titre du document dans la barre de titre de la fenêtre lors de la conversion au format PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes pour afficher le titre du document dans la barre de titre de la fenêtre avec Aspose.Words pour .NET. Cette fonctionnalité vous permet d'afficher le titre du document dans la barre de titre de la fenêtre lorsque vous ouvrez le document PDF généré. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin d'accès correct à votre document.

## Étape 2 : Configurer les options d'enregistrement PDF

Créez une instance de la classe PdfSaveOptions et activez l'affichage du titre du document dans la barre de titre de la fenêtre :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Cette option active l'affichage du titre du document dans la barre de titre de la fenêtre lors de la conversion au format PDF.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options de conversion :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le PDF converti.

### Exemple de code source pour Afficher le titre du document dans la barre de titre de la fenêtre à l'aide de Aspose.Words pour .NET

Voici le code source complet pour afficher le titre du document dans la barre de titre de la fenêtre dans un document PDF avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
En suivant ces étapes, vous pouvez facilement afficher le titre du document dans la barre de titre de la fenêtre lors de la conversion au format PDF avec Aspose.Words pour .NET.

