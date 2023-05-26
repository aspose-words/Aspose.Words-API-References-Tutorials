---
title: Conversion en PDF 17
linktitle: Conversion en PDF 17
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des documents au format PDF 1.7 avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

Dans ce didacticiel, nous vous guiderons à travers les étapes de conversion au format PDF 1.7 avec Aspose.Words pour .NET. La conversion au format PDF 1.7 vous permet de générer des fichiers PDF conformes à la norme PDF 1.7. Suivez les étapes ci-dessous :

## Étape 1 : Chargement du document

Commencez par télécharger le document que vous souhaitez convertir en PDF :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assurez-vous de spécifier le chemin d'accès correct à votre document.

## Étape 2 : Définir les options de conversion PDF

Créez une instance de la classe PdfSaveOptions et spécifiez la version de la norme PDF que vous souhaitez utiliser :

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Cette option garantit que le fichier PDF généré est conforme à la norme PDF 1.7.

## Étape 3 : Convertir le document en PDF

 Utilisez le`Save` méthode pour convertir le document en PDF en spécifiant les options de conversion :

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le PDF converti.

### Exemple de code source pour la conversion en PDF 17 en utilisant Aspose.Words pour .NET

Voici le code source complet pour convertir en PDF 1.7 avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

En suivant ces étapes, vous pouvez facilement convertir en PDF 1.7 avec Aspose.Words pour .NET.

