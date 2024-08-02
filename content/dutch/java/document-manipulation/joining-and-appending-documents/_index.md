---
title: Documenten samenvoegen en toevoegen in Aspose.Words voor Java
linktitle: Documenten samenvoegen en toevoegen
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u moeiteloos documenten kunt samenvoegen en toevoegen met Aspose.Words voor Java. Behoud de opmaak, beheer kopteksten, voetteksten en meer.
type: docs
weight: 30
url: /nl/java/document-manipulation/joining-and-appending-documents/
---

## Inleiding tot het samenvoegen en toevoegen van documenten in Aspose.Words voor Java

In deze zelfstudie onderzoeken we hoe u documenten kunt samenvoegen en toevoegen met behulp van de Aspose.Words voor Java-bibliotheek. U leert hoe u meerdere documenten naadloos kunt samenvoegen met behoud van de opmaak en structuur.

## Vereisten

Voordat we beginnen, zorg ervoor dat Aspose.Words voor Java API is ingesteld in uw Java-project.

## Opties voor het samenvoegen van documenten

### Eenvoudig toevoegen

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Voeg toe met importformaatopties

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### Toevoegen aan leeg document

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Voeg toe met paginanummerconversie

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // Converteer NUMAGES-velden
dstDoc.updatePageLayout(); // Update de pagina-indeling voor correcte nummering
```

## Omgaan met verschillende pagina-instellingen

Bij het toevoegen van documenten met verschillende pagina-instellingen:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// Zorg ervoor dat de instellingen voor de pagina-instelling overeenkomen met het doeldocument
```

## Documenten met verschillende stijlen samenvoegen

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## Slim stijlgedrag

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## Documenten invoegen met DocumentBuilder

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Bronnummering behouden

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Omgaan met tekstvakken

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Kop- en voetteksten beheren

### Kop- en voetteksten koppelen

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Kop- en voetteksten ontkoppelen

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Conclusie

Aspose.Words voor Java biedt flexibele en krachtige tools voor het samenvoegen en toevoegen van documenten, of u nu de opmaak wilt behouden, verschillende pagina-instellingen wilt beheren of kop- en voetteksten wilt beheren. Experimenteer met deze technieken om aan uw specifieke documentverwerkingsbehoeften te voldoen.

## Veelgestelde vragen

### Hoe kan ik documenten met verschillende stijlen naadloos aan elkaar koppelen?

 Gebruik om documenten met verschillende stijlen samen te voegen`ImportFormatMode.USE_DESTINATION_STYLES` bij het toevoegen.

### Kan ik de paginanummering behouden bij het toevoegen van documenten?

 Ja, u kunt de paginanummering behouden door gebruik te maken van de`convertNumPageFieldsToPageRef` methode en het bijwerken van de pagina-indeling.

### Wat is slim stijlgedrag?

 Slim stijlgedrag zorgt ervoor dat consistente stijlen behouden blijven bij het toevoegen van documenten. Gebruik het met`ImportFormatOptions` voor betere resultaten.

### Hoe kan ik omgaan met tekstvakken bij het toevoegen van documenten?

Set`importFormatOptions.setIgnoreTextBoxes(false)` om tekstvakken op te nemen tijdens het toevoegen.

### Wat moet ik doen als ik kop- en voetteksten tussen documenten wil koppelen/ontkoppelen?

 U kunt kop- en voetteksten koppelen met`linkToPrevious(true)` of ontkoppel ze`linkToPrevious(false)` zoals nodig.