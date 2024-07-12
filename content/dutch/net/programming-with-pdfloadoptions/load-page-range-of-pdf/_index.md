---
title: Paginabereik van pdf laden
linktitle: Paginabereik van pdf laden
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het laden van een specifiek PDF-paginabereik met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

In deze zelfstudie laten we u zien hoe u een specifiek paginabereik uit een PDF-document kunt laden met Aspose.Words voor .NET. Volg onderstaande stappen:

## Stap 1: Een reeks PDF-pagina's laden

Gebruik de volgende code om een specifiek paginabereik uit een PDF-document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 In dit voorbeeld laden we de eerste pagina van het PDF-document. U kunt de waarden van wijzigen`PageIndex`En`PageCount` naar het gewenste paginabereik.

## Stap 2: Het document opslaan

 Ten slotte kunt u het document met het specifieke paginabereik opslaan met behulp van de`Save` methode:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Zorg ervoor dat u het juiste pad opgeeft om het bewerkte document op te slaan.

Dat is alles ! U hebt nu een specifiek paginabereik uit een PDF-document geladen met Aspose.Words voor .NET.

### Voorbeeldbroncode voor het laden van paginabereik van pdf met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Vergeet niet het juiste pad naar de directory van uw PDF-documenten op te geven.



