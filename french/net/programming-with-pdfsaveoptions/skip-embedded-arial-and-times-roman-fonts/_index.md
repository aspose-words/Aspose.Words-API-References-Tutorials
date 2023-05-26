---
title: Ignorer les polices Arial et Times Roman intégrées
linktitle: Ignorer les polices Arial et Times Roman intégrées
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour générer un PDF sans incorporer les polices Arial et Times Roman avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Cet article fournit un guide étape par étape sur la façon d'utiliser la fonctionnalité pour ignorer les polices Arial et Times Roman intégrées à la taille du métafichier avec Aspose.Words pour .NET. Nous expliquerons chaque partie du code en détail. À la fin de ce didacticiel, vous serez en mesure de comprendre comment configurer l'option du mode d'incorporation des polices dans un document et générer un PDF sans incorporer les polices Arial et Times Roman.

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

## Étape 3 : Configurer les options d'enregistrement au format PDF avec incorporation de polices

 Pour ignorer l'intégration des polices Arial et Times Roman dans le PDF généré, nous devons configurer le`PdfSaveOptions` objet et définissez le`FontEmbeddingMode` propriété à`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Étape 4 : Enregistrez le document au format PDF sans polices intégrées

Enfin, nous pouvons enregistrer le document au format PDF en utilisant les options d'enregistrement configurées précédemment.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

C'est tout ! Vous avez généré avec succès un PDF sans incorporer les polices Arial et Times Roman à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour ignorer les polices Arial et Times Roman intégrées à la taille du métafichier avec Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```
