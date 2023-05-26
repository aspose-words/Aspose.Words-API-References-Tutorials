---
title: Définir les options de contour
linktitle: Définir les options de contour
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour définir les options de plan dans un document PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/set-outline-options/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser les options de contour définies pour la fonctionnalité de taille de métafichier avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment définir les options de contour dans un document et générer un PDF avec les options de contour correspondantes.

Avant de commencer, assurez-vous d'avoir installé et configuré la bibliothèque Aspose.Words pour .NET dans votre projet. Vous pouvez trouver la bibliothèque et les instructions d'installation sur le site Web d'Aspose.

## Étape 1 : Définir le répertoire des documents

 Pour commencer, vous devez définir le chemin vers le répertoire où se trouvent vos documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Téléchargez le document

Ensuite, nous devons charger le document que nous voulons traiter. Dans cet exemple, nous supposons que le document s'appelle "Rendering.docx" et se trouve dans le répertoire de documents spécifié.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Étape 3 : Configurer les options d'enregistrement au format PDF avec les options de plan

 Pour définir les options de contour dans le PDF généré, nous devons configurer le`PdfSaveOptions` objet. Nous pouvons définir le nombre de niveaux de contour de titre (`HeadingsOutlineLevels`) et le nombre de niveaux hiérarchiques développés (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Étape 4 : Enregistrer le document au format PDF avec les options de plan

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options d'enregistrement configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

C'est tout ! Vous avez défini avec succès les options de plan dans un document et généré un PDF avec les options de plan correspondantes à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour définir les options de plan sur la taille du métafichier avec Aspose.Words pour .NET


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```
