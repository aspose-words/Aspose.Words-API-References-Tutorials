---
title: Charger la plage de pages du pdf
linktitle: Charger la plage de pages du pdf
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour charger une plage de pages PDF spécifique avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

Dans ce didacticiel, nous vous expliquerons comment charger une plage de pages spécifique à partir d'un document PDF à l'aide de Aspose.Words pour .NET. Suivez les étapes ci-dessous :

## Étape 1 : Charger une série de pages PDF

Utilisez le code suivant pour charger une plage de pages spécifique à partir d'un document PDF :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 Dans cet exemple, nous chargeons la première page du document PDF. Vous pouvez modifier les valeurs de`PageIndex` et`PageCount` à la plage de pages souhaitée.

## Étape 2 : Enregistrer le document

 Enfin, vous pouvez enregistrer le document contenant la plage de pages spécifique à l'aide de la`Save` méthode:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Assurez-vous de spécifier le chemin d'accès correct pour enregistrer le document modifié.

C'est tout ! Vous avez maintenant chargé une plage de pages spécifique à partir d'un document PDF à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Load Page Range Of Pdf en utilisant Aspose.Words pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
N'oubliez pas de spécifier le chemin d'accès correct au répertoire de vos documents PDF.



