---
title: Polices de sous-ensemble intégrées
linktitle: Polices de sous-ensemble intégrées
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour incorporer des sous-ensembles de polices dans un PDF à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Cet article fournit un guide étape par étape sur l'utilisation de la fonctionnalité d'incorporation de sous-ensemble de polices avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment intégrer des sous-ensembles de polices dans un document et générer un PDF contenant uniquement les glyphes utilisés dans le document.

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

## Étape 3 : Configurer les options d'enregistrement au format PDF

 Pour créer un PDF contenant uniquement les sous-ensembles de polices utilisées dans le document, nous devons configurer le`PdfSaveOptions` objet avec le`EmbedFullFonts` propriété définie sur`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Étape 4 : Enregistrer le document au format PDF avec des sous-ensembles de polices

 Enfin, nous pouvons enregistrer le document au format PDF en utilisant les sous-ensembles de polices. Spécifiez le nom du fichier de sortie et le`saveOptions` objet que nous avons configuré à l'étape précédente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

C'est tout ! Vous avez intégré avec succès des sous-ensembles de polices dans un document et généré un PDF contenant uniquement les glyphes utilisés dans le document avec Aspose.Words pour .NET.

### Exemple de code source pour incorporer des sous-ensembles de polices avec Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Le PDF de sortie contiendra des sous-ensembles des polices du document.
	// Seuls les glyphes utilisés dans le document sont inclus dans les polices PDF.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```
