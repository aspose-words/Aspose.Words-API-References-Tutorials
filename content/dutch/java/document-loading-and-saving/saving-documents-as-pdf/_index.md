---
title: Documenten opslaan als PDF in Aspose.Words voor Java
linktitle: Documenten opslaan als PDF
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u Word-documenten als PDF kunt opslaan met Aspose.Words voor Java. Pas lettertypen, eigenschappen en afbeeldingskwaliteit aan. Een uitgebreide gids voor PDF-conversie.
type: docs
weight: 22
url: /nl/java/document-loading-and-saving/saving-documents-as-pdf/
---

## Inleiding tot het opslaan van documenten als PDF in Aspose.Words voor Java

In deze stapsgewijze handleiding onderzoeken we hoe u documenten als PDF kunt opslaan met Aspose.Words voor Java. We bespreken verschillende aspecten van PDF-conversie en geven codevoorbeelden om het proces eenvoudiger te maken.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.Words voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/words/java/).

## Een document naar PDF converteren

Om een Word-document naar PDF te converteren, kunt u het volgende codefragment gebruiken:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Vervangen`"input.docx"` met het pad naar uw Word-document en`"output.pdf"` met het gewenste uitvoer-PDF-bestandspad.

## Opties voor het opslaan van PDF's beheren

 U kunt verschillende opties voor het opslaan van PDF's beheren met behulp van de`PdfSaveOptions` klas. U kunt de weergavetitel voor het PDF-document bijvoorbeeld als volgt instellen:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## Lettertypen in PDF insluiten

Gebruik de volgende code om lettertypen in de gegenereerde PDF in te sluiten:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## Documenteigenschappen aanpassen

U kunt documenteigenschappen in de gegenereerde PDF aanpassen. Bijvoorbeeld:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## Documentstructuur exporteren

 Om de documentstructuur te exporteren, stelt u de`exportDocumentStructure` optie om`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## Beeldcompressie

U kunt de beeldcompressie regelen met behulp van de volgende code:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## Laatste afgedrukte eigenschap bijwerken

Om de eigenschap "Laatst afgedrukt" in de PDF bij te werken, gebruikt u:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## DML 3D-effecten renderen

Voor geavanceerde weergave van DML 3D-effecten stelt u de weergavemodus in:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## Afbeeldingen interpoleren

U kunt beeldinterpolatie inschakelen om de beeldkwaliteit te verbeteren:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## Conclusie

Aspose.Words voor Java biedt uitgebreide mogelijkheden voor het converteren van Word-documenten naar PDF-formaat met flexibiliteit en aanpassingsopties. U kunt verschillende aspecten van de PDF-uitvoer beheren, waaronder lettertypen, documenteigenschappen, afbeeldingscompressie en meer.

## Veelgestelde vragen

### Hoe converteer ik een Word-document naar PDF met Aspose.Words voor Java?

Gebruik de volgende code om een Word-document naar PDF te converteren:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Vervangen`"input.docx"` met het pad naar uw Word-document en`"output.pdf"` met het gewenste uitvoer-PDF-bestandspad.

### Kan ik lettertypen insluiten in de PDF die is gegenereerd door Aspose.Words voor Java?

 Ja, u kunt lettertypen inde PDF insluiten door de`setEmbedFullFonts` optie om`true` in `PdfSaveOptions`. Hier is een voorbeeld:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### Hoe kan ik documenteigenschappen in de gegenereerde PDF aanpassen?

 U kunt documenteigenschappen in de PDF aanpassen met behulp van de`setCustomPropertiesExport` optie in`PdfSaveOptions`. Bijvoorbeeld:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### Wat is het doel van beeldcompressie in Aspose.Words voor Java?

 Met beeldcompressie kunt u de kwaliteit en grootte van afbeeldingen inde gegenereerde PDF bepalen. U kunt de beeldcompressiemodus instellen met`setImageCompression` in `PdfSaveOptions`.

### Hoe werk ik de eigenschap "Laatst afgedrukt" in de PDF bij?

 U kunt de eigenschap "Laatst afgedrukt" inde PDF bijwerken door in te stellen`setUpdateLastPrintedProperty` naar`true` in `PdfSaveOptions`. Dit weerspiegelt de laatst afgedrukte datum in de PDF-metagegevens.

### Hoe kan ik de beeldkwaliteit verbeteren bij het converteren naar PDF?

 Om de beeldkwaliteit te verbeteren, schakelt u beeldinterpolatie indoor in te stellen`setInterpolateImages` naar`true` in `PdfSaveOptions`. Dit resulteert in vloeiendere afbeeldingen van hogere kwaliteit in de PDF.