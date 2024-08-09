---
title: Documentwatermerken en pagina-instelling
linktitle: Documentwatermerken en pagina-instelling
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u watermerken kunt toepassen en paginaconfiguraties kunt instellen met Aspose.Words voor Java. Een uitgebreide handleiding met broncode.
type: docs
weight: 13
url: /nl/java/document-styling/document-watermarking-page-setup/
---
## Invoering

Op het gebied van documentmanipulatie is Aspose.Words voor Java een krachtig hulpmiddel waarmee ontwikkelaars controle kunnen uitoefenen over elk aspect van documentverwerking. In deze uitgebreide handleiding gaan we dieper in op de fijne kneepjes van het watermerken van documenten en het instellen van pagina's met behulp van Aspose.Words voor Java. Of u nu een doorgewinterde ontwikkelaar bent of net de wereld van Java-documentverwerking betreedt, deze stapsgewijze handleiding voorziet u van de kennis en broncode die u nodig heeft.

## Documentwatermerken

### Watermerken toevoegen

Het toevoegen van watermerken aan documenten kan van cruciaal belang zijn voor de branding of beveiliging van uw inhoud. Aspose.Words voor Java maakt deze taak eenvoudig. Hier ziet u hoe:

```java
// Laad het document
Document doc = new Document("document.docx");

// Maak een watermerk
Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.getTextPath().setText("Confidential");
watermark.setWidth(300);
watermark.setHeight(100);

// Plaats het watermerk
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.setWrapType(WrapType.NONE);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);

// Plaats het watermerk
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Bewaar het document
doc.save("document_with_watermark.docx");
```

### Watermerken aanpassen

U kunt watermerken verder aanpassen door het lettertype, de grootte, de kleur en de rotatie aan te passen. Deze flexibiliteit zorgt ervoor dat uw watermerk naadloos aansluit bij de stijl van uw document.

## Pagina-instelling

### Paginagrootte en richting

Pagina-instelling is cruciaal bij de documentopmaak. Aspose.Words voor Java biedt volledige controle over paginagrootte en -oriëntatie:

```java
// Laad het document
Document doc = new Document("document.docx");

// Stel het paginaformaat in op A4
doc.getFirstSection().getPageSetup().setPageWidth(595.0);
doc.getFirstSection().getPageSetup().setPageHeight(842.0);

// Wijzig de paginarichting naar liggend
doc.getFirstSection().getPageSetup().setOrientation(Orientation.LANDSCAPE);

// Sla het gewijzigde document op
doc.save("formatted_document.docx");
```

### Marges en paginanummering

Nauwkeurige controle over marges en paginanummering is essentieel voor professionele documenten. Bereik dit met Aspose.Words voor Java:

```java
// Laad het document
Document doc = new Document("document.docx");

// Marges instellen
doc.getFirstSection().getPageSetup().setLeftMargin(72.0);
doc.getFirstSection().getPageSetup().setRightMargin(72.0);
doc.getFirstSection().getPageSetup().setTopMargin(72.0);
doc.getFirstSection().getPageSetup().setBottomMargin(72.0);

// Paginanummering inschakelen
doc.getFirstSection().getPageSetup().setDifferentFirstPageHeaderFooter(true);
HeaderFooter firstPageHeader = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_FIRST);
firstPageHeader.appendParagraph("First Page Header");

// Sla het opgemaakte document op
doc.save("formatted_document.docx");
```

## Veelgestelde vragen

### Hoe kan ik een watermerk uit een document verwijderen?

Als u een watermerk uit een document wilt verwijderen, kunt u de vormen van het document doorlopen en de vormen verwijderen die watermerken vertegenwoordigen. Hier is een fragment:

```java
Document doc = new Document("document_with_watermark.docx");

for (Shape shape : doc.getChildNodes(NodeType.SHAPE, true).<Shape>toArray()) {
    if (shape.getText().contains("Confidential")) {
        shape.remove();
    }
}

doc.save("document_without_watermark.docx");
```

### Kan ik meerdere watermerken aan één document toevoegen?

Ja, u kunt meerdere watermerken aan een document toevoegen door extra Shape-objecten te maken en deze naar wens te positioneren.

### Hoe wijzig ik het paginaformaat naar Legal in liggende richting?

Om het paginaformaat in liggende richting in te stellen op Legal, wijzigt u de paginabreedte en -hoogte als volgt:

```java
doc.getFirstSection().getPageSetup().setPageWidth(842.0);
doc.getFirstSection().getPageSetup().setPageHeight(595.0);
```

### Wat is het standaardlettertype voor watermerken?

Het standaardlettertype voor watermerken is Calibri met een lettergrootte van 36.

### Hoe kan ik paginanummers toevoegen vanaf een specifieke pagina?

U kunt dit bereiken door het startpaginanummer in uw document als volgt in te stellen:

```java
doc.getFirstSection().getPageSetup().setPageStartingNumber(5);
```

### Hoe kan ik tekst in de kop- of voettekst centreren?

U kunt tekst in de kop- of voettekst centreren met behulp van de setAlignment-methode voor het Paragraph-object in de kop- of voettekst.

## Conclusie

In deze uitgebreide handleiding hebben we de kunst van het watermerken van documenten en het instellen van pagina's onderzocht met behulp van Aspose.Words voor Java. Gewapend met de meegeleverde broncodefragmenten en inzichten beschikt u nu over de tools om uw documenten met finesse te manipuleren en op te maken. Met Aspose.Words voor Java kunt u professionele, merkdocumenten maken die zijn afgestemd op uw exacte specificaties.

Het beheersen van documentmanipulatie is een waardevolle vaardigheid voor ontwikkelaars, en Aspose.Words voor Java is uw vertrouwde metgezel op deze reis. Begin vandaag nog met het maken van verbluffende documenten!