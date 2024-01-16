---
title: Exporteer Word-documentkoptekst en voettekstbladwijzers naar PDF-document
linktitle: Exporteer Word-documentkoptekst en voettekstbladwijzers naar PDF-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het exporteren van word-documentkoptekst-voettekstbladwijzers naar pdf-documentbladwijzers met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Dit artikel biedt een stapsgewijze handleiding voor het exporteren van bladwijzers van de koptekst en voettekst van Word-documenten naar de pdf-documentfunctie met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze zelfstudie begrijpt u hoe u bladwijzers uit de kop- en voetteksten van een document kunt exporteren en een PDF met de juiste bladwijzers kunt genereren.

Zorg ervoor dat u, voordat u begint, de Aspose.Words voor .NET-bibliotheek in uw project hebt geïnstalleerd en geconfigureerd. U kunt de bibliotheek en installatie-instructies vinden op de Aspose-website.

## Stap 1: Definieer de documentmap

 Om te beginnen moet u het pad definiëren naar de map waar uw documenten zich bevinden. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Upload het document

Vervolgens moeten we het document laden dat we willen verwerken. In dit voorbeeld gaan we ervan uit dat het document "Bladwijzers in kop- en voetteksten.docx" heet en zich in de opgegeven documentenmap bevindt.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Stap 3: Configureer de opties voor opslaan als PDF

 Om kop- en voettekstbladwijzers te exporteren, moeten we de`PdfSaveOptions` voorwerp. In dit voorbeeld stellen we het standaardoverzichtsniveau van de bladwijzer in op 1 en de bladwijzerexportmodus voor kop- en voettekst op 'Eerste'.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Stap 4: Sla het document op als PDF met bladwijzers voor kop- en voetteksten

Ten slotte kunnen we het document in PDF-formaat opslaan met behulp van de eerder geconfigureerde opslagopties.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Dat is alles ! U hebt met succes kop- en voettekstbladwijzers uit een document geëxporteerd en een PDF met de juiste bladwijzers gegenereerd met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor het exporteren van kop- en voettekstbladwijzers met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Conclusie

In deze zelfstudie hebben we uitgelegd hoe u kop- en voettekstbladwijzers kunt exporteren van een Word-document naar een PDF-document met behulp van Aspose.Words voor .NET. Geëxporteerde bladwijzers maken eenvoudige navigatie en snelle verwijzing naar overeenkomstige kop- en voetteksten in het gegenereerde PDF-document mogelijk. Volg de beschreven stappen om kop- en voettekstbladwijzers uit een document te exporteren en een PDF met de juiste bladwijzers te genereren met behulp van Aspose.Words voor .NET. Zorg ervoor dat u het juiste pad naar uw documenten opgeeft en configureer indien nodig de opslagopties.

### Veel Gestelde Vragen

### Vraag: Wat is het exporteren van kop- en voettekstbladwijzers van een Word-document naar een PDF-document?
A: Het exporteren van bladwijzers voor kop- en voetteksten van een Word-document naar een PDF-document is een functie waarmee u bladwijzers in het PDF-document kunt bewaren en genereren op basis van de kop- en voetteksten. voetteksten van het originele Word-document. Hierdoor kunnen gebruikers snel en eenvoudig door het PDF-document navigeren met behulp van bladwijzers die overeenkomen met kop- en voetteksten.

### Vraag: Hoe kan ik Aspose.Words voor .NET gebruiken om kop- en voettekstbladwijzers van een Word-document naar een PDF-document te exporteren?
A: Volg deze stappen om kop- en voettekstbladwijzers van een Word-document naar een PDF-document te exporteren met Aspose.Words voor .NET:

 Stel het mappad in waar uw documenten zich bevinden door te vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad van uw documentenmap.

 Laad het document dat u wilt verwerken met behulp van de`Document` class en specificeer het pad naar het Word-document in de opgegeven documentenmap.

 Configureer de opties voor opslaan als PDF door een exemplaar te maken van het`PdfSaveOptions` klasse en het instellen van de juiste bladwijzeropties voor kop- en voettekst.

 Sla het document op in PDF-formaat met behulp van de`Save` werkwijze van de`Document` klasse die het pad specificeert en opties voor opslaan.

### Vraag: Wat zijn de voordelen van het exporteren van kop- en voettekstbladwijzers naar een PDF-document?
A: De voordelen van het exporteren van kop- en voettekstbladwijzers naar een PDF-document zijn:

Eenvoudige navigatie: Met bladwijzers kunnen gebruikers eenvoudig door een PDF-document navigeren door naar specifieke kop- en voetteksten te verwijzen.

Snelle referentie: Met bladwijzers kunnen gebruikers snel relevante secties van het PDF-document vinden op basis van kop- en voetteksten.