---
title: Désactiver les polices Windows intégrées
linktitle: Désactiver les polices Windows intégrées
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment désactiver l'incorporation de polices Windows lors de la conversion de documents au format PDF avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes pour désactiver l'incorporation de polices Windows dans un document PDF avec Aspose.Words pour .NET. En désactivant l'incorporation des polices, vous pouvez réduire la taille du fichier PDF généré. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin d'accès correct à votre document.

## Étape 2 : Définir les options d'enregistrement PDF

Créez une instance de la classe PdfSaveOptions et spécifiez comment incorporer les polices :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Cette option permet de désactiver l'intégration des polices Windows dans le fichier PDF généré.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options de conversion :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le PDF converti.

### Exemple de code source pour désactiver les polices Windows intégrées à l'aide de Aspose.Words pour .NET

Voici le code source complet pour désactiver l'intégration des polices Windows dans un document PDF avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Le PDF de sortie sera enregistré sans incorporer les polices Windows standard.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
En suivant ces étapes, vous pouvez facilement désactiver l'incorporation des polices Windows dans un document PDF avec Aspose.Words pour .NET.

