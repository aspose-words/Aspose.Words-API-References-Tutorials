---
title: Charger la plage de pages du PDF
linktitle: Charger la plage de pages du PDF
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour charger une plage de pages PDF spécifique avec Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

Dans ce didacticiel, nous vous expliquerons comment charger une plage de pages spécifique à partir d'un document PDF à l'aide d'Aspose.Words pour .NET. Suivez les étapes ci-dessous :

## Étape 1 : Chargement d'une série de pages PDF

Utilisez le code suivant pour charger une plage de pages spécifique à partir d'un document PDF :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 Dans cet exemple, nous chargeons la première page du document PDF. Vous pouvez modifier les valeurs de`PageIndex` et`PageCount` à la plage de pages souhaitée.

## Étape 2 : Sauvegarde du document

 Enfin, vous pouvez enregistrer le document contenant la plage de pages spécifique à l'aide du`Save` méthode:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Assurez-vous de spécifier le chemin correct pour enregistrer le document modifié.

C'est tout ! Vous avez maintenant chargé une plage de pages spécifique à partir d'un document PDF à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour charger une plage de pages de PDF à l'aide d'Aspose.Words pour .NET

```csharp

	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
N'oubliez pas de préciser le chemin correct vers le répertoire de vos documents PDF.



