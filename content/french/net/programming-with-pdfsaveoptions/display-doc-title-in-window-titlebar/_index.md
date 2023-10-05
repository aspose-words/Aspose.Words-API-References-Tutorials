---
title: Afficher le titre du document dans la barre de titre de la fenêtre
linktitle: Afficher le titre du document dans la barre de titre de la fenêtre
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment afficher le titre du document dans la barre de titre de la fenêtre lors de la conversion en PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes pour afficher le titre du document dans la barre de titre de la fenêtre avec Aspose.Words for .NET. Cette fonctionnalité vous permet d'afficher le titre du document dans la barre de titre de la fenêtre lorsque vous ouvrez le document PDF généré. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin correct vers votre document.

## Étape 2 : Configurer les options d'enregistrement PDF

Créez une instance de la classe PdfSaveOptions et activez l'affichage du titre du document dans la barre de titre de la fenêtre :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Cette option permet l'affichage du titre du document dans la barre de titre de la fenêtre lors de la conversion en PDF.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options de conversion :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin correct pour enregistrer le PDF converti.

### Exemple de code source pour afficher le titre du document dans la barre de titre de la fenêtre à l'aide d'Aspose.Words pour .NET

Voici le code source complet pour afficher le titre du document dans la barre de titre de la fenêtre dans un document PDF avec Aspose.Words for .NET :

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
En suivant ces étapes, vous pouvez facilement afficher le titre du document dans la barre de titre de la fenêtre lors de la conversion en PDF avec Aspose.Words pour .NET.

### Questions fréquemment posées

#### Q : Qu'est-ce que la fonctionnalité « Afficher le titre du document dans la barre de titre de la fenêtre » avec Aspose.Words pour .NET ?
La fonctionnalité « Afficher le titre du document dans la barre de titre de la fenêtre » avec Aspose.Words for .NET vous permet d'afficher le titre du document dans la barre de titre de la fenêtre lorsque vous ouvrez le document PDF généré. Cela facilite l'identification et la distinction des documents PDF dans votre environnement de lecture.

#### Q : Comment puis-je utiliser cette fonctionnalité avec Aspose.Words pour .NET ?
Pour utiliser cette fonctionnalité avec Aspose.Words for .NET, procédez comme suit :

 Chargez le document à l'aide du`Document` et en spécifiant le chemin du fichier à convertir en PDF.

 Configurez les options d'enregistrement PDF en créant une instance du`PdfSaveOptions` classe et définir le`DisplayDocTitle`propriété à`true`. Cela permet l'affichage du titre du document dans la barre de titre de la fenêtre lors de la conversion en PDF.

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options de conversion.

#### Q : Cette fonctionnalité modifie-t-elle le contenu du document lui-même ?
Non, cette fonctionnalité ne modifie pas le contenu du document lui-même. Cela n'affecte que l'affichage du titre du document dans la barre de titre de la fenêtre lorsqu'il est ouvert en tant que document PDF. Le contenu du document reste inchangé.

#### Q : Est-il possible de personnaliser le titre du document affiché dans la barre de titre de la fenêtre ?
 Oui, vous pouvez personnaliser le titre du document affiché dans la barre de titre de la fenêtre en modifiant le`Document.Title` propriété du document avant de le convertir en PDF. Vous pouvez définir le titre souhaité à l'aide d'une chaîne. Assurez-vous de définir le titre avant d'appeler le`Save` méthode de conversion en PDF.

#### Q : Quels autres formats de sortie Aspose.Words prend-il en charge pour la conversion de documents ?
Aspose.Words for .NET prend en charge de nombreux formats de sortie pour la conversion de documents, tels que PDF, XPS, HTML, EPUB, MOBI, image (JPEG, PNG, BMP, TIFF, GIF) et bien d'autres. d'autres encore. Vous pouvez choisir le format de sortie approprié en fonction de vos besoins spécifiques.