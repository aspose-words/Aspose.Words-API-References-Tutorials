---
title: Tabellen en tabelstijlen opmaken
linktitle: Tabellen en tabelstijlen opmaken
second_title: Aspose.Words Java Documentverwerkings-API
description: Leer hoe u tabellen opmaakt en stijlen toepast met Aspose.Words voor Java. Deze stapsgewijze handleiding behandelt het instellen van randen, het arceren van cellen en het toepassen van tabelstijlen.
type: docs
weight: 17
url: /nl/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Invoering

Als het gaat om documentopmaak, spelen tabellen een cruciale rol bij het organiseren en duidelijk presenteren van gegevens. Als u met Java en Aspose.Words werkt, hebt u krachtige tools tot uw beschikking voor het maken en opmaken van tabellen in uw documenten. Of u nu een eenvoudige tabel ontwerpt of geavanceerde stijlen toepast, Aspose.Words voor Java biedt een scala aan functies om u te helpen professioneel ogende resultaten te behalen.

In deze gids leiden we u door het proces van het opmaken van tabellen en het toepassen van tabelstijlen met Aspose.Words voor Java. U leert hoe u tabelranden instelt, celschaduw toepast en tabelstijlen gebruikt om het uiterlijk van uw documenten te verbeteren. Aan het einde hebt u de vaardigheden om goed opgemaakte tabellen te maken die uw gegevens laten opvallen.

## Vereisten

Voordat we beginnen, zijn er een paar dingen die u moet regelen:

1. Java Development Kit (JDK): Zorg ervoor dat u JDK 8 of later hebt geïnstalleerd. Aspose.Words voor Java vereist een compatibele JDK om correct te kunnen werken.
2. Integrated Development Environment (IDE): Een IDE zoals IntelliJ IDEA of Eclipse helpt u bij het beheren van uw Java-projecten en het stroomlijnen van uw ontwikkelingsproces.
3.  Aspose.Words voor Java-bibliotheek: download de nieuwste versie van Aspose.Words voor Java[hier](https://releases.aspose.com/words/java/) en neem het op in uw project.
4. Voorbeeldcode: We gebruiken een aantal voorbeeldcodefragmenten, dus zorg ervoor dat u een basiskennis hebt van Java-programmering en hoe u bibliotheken in uw project kunt integreren.

## Pakketten importeren

Om met Aspose.Words voor Java te werken, moet u de relevante pakketten in uw project importeren. Deze pakketten bieden de klassen en methoden die nodig zijn voor het manipuleren en formatteren van documenten.

```java
import com.aspose.words.*;
```

Met deze importinstructie krijgt u toegang tot alle essentiële klassen die nodig zijn voor het maken en opmaken van tabellen in uw documenten.

## Stap 1: Tabellen opmaken

Het opmaken van tabellen in Aspose.Words voor Java omvat het instellen van randen, het arceren van cellen en het toepassen van verschillende opmaakopties. Dit is hoe u het kunt doen:

### Laad het document

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### De tabel maken en formatteren

```java
Table table = builder.startTable();
builder.insertCell();

// Stel de randen voor de hele tabel in.
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
        
// Stel de celarcering voor deze cel in.
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
builder.writeln("Cell #1");

builder.insertCell();
        
// Geef een andere celarcering op voor de tweede cel.
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");

builder.endRow();
```

### Pas celranden aan

```java
// Wis de celopmaak van eerdere bewerkingen.
builder.getCellFormat().clearFormatting();

builder.insertCell();

// Maak grotere randen voor de eerste cel van deze rij.
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");

builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
        
doc.save("FormatTableAndCellWithDifferentBorders.docx");
```

### Uitleg

In dit voorbeeld:
- Randen instellen: We stellen de randen van de gehele tabel in op een enkele lijnstijl met een dikte van 2,0 punten.
- Cell Shading: De eerste cel is rood gearceerd en de tweede cel is groen gearceerd. Dit helpt om visueel onderscheid te maken tussen cellen.
- Celranden: Voor de derde cel maken we dikkere randen, zodat deze zich onderscheidt van de rest.

## Stap 2: Tabelstijlen toepassen

Tabelstijlen in Aspose.Words voor Java stellen u in staat om vooraf gedefinieerde opmaakopties toe te passen op tabellen, waardoor het eenvoudiger wordt om een consistente look te bereiken. Zo past u een stijl toe op uw tabel:

### Maak het document en de tabel

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.startTable();
        
// We moeten eerst minimaal één rij invoegen voordat we de tabelopmaak kunnen instellen.
builder.insertCell();
```

### Tabelstijl toepassen

```java
// Stel de tabelstijl in op basis van een unieke stijl-ID.
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
        
// Bepaal welke functies door de stijl moeten worden opgemaakt.
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
table.autoFit(AutoFitBehavior.AUTO_FIT_TO_CONTENTS);
```

### Tabelgegevens toevoegen

```java
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
builder.endRow();

builder.insertCell();
builder.writeln("Apples");
builder.insertCell();
builder.writeln("20");
builder.endRow();

builder.insertCell();
builder.writeln("Bananas");
builder.insertCell();
builder.writeln("40");
builder.endRow();

builder.insertCell();
builder.writeln("Carrots");
builder.insertCell();
builder.writeln("50");
builder.endRow();

doc.save("BuildTableWithStyle.docx");
```

### Uitleg

In dit voorbeeld:
- Tabelstijl instellen: We passen een vooraf gedefinieerde stijl toe (`MEDIUM_SHADING_1_ACCENT_1`) naar de tabel. Deze stijl omvat opmaak voor verschillende delen van de tabel.
- Stijlopties: We geven aan dat de eerste kolom, rijbanden en eerste rij moeten worden opgemaakt volgens de stijlopties.
-  AutoFit: Wij gebruiken`AUTO_FIT_TO_CONTENTS` om ervoor te zorgen dat de tabelgrootte wordt aangepast op basis van de inhoud.

## Conclusie

En daar heb je het! Je hebt succesvol tabellen geformatteerd en stijlen toegepast met Aspose.Words voor Java. Met deze technieken kun je tabellen maken die niet alleen functioneel zijn, maar ook visueel aantrekkelijk. Het effectief formatteren van tabellen kan de leesbaarheid en professionele uitstraling van je documenten enorm verbeteren.

Aspose.Words voor Java is een robuuste tool die uitgebreide functies biedt voor documentmanipulatie. Door tabelopmaak en -stijlen onder de knie te krijgen, bent u een stap dichter bij het benutten van de volledige kracht van deze bibliotheek.

## Veelgestelde vragen

### 1. Kan ik aangepaste tabelstijlen gebruiken die niet in de standaardopties zijn opgenomen?

 Ja, u kunt aangepaste stijlen definiëren en toepassen op uw tabellen met Aspose.Words voor Java. Controleer de[documentatie](https://reference.aspose.com/words/java/) voor meer informatie over het maken van aangepaste stijlen.

### 2. Hoe kan ik voorwaardelijke opmaak toepassen op tabellen?

Met Aspose.Words voor Java kunt u de tabelopmaak programmatisch aanpassen op basis van voorwaarden. Dit kunt u doen door specifieke criteria in uw code te controleren en de opmaak dienovereenkomstig toe te passen.

### 3. Kan ik samengevoegde cellen in een tabel opmaken?

Ja, u kunt samengevoegde cellen opmaken zoals gewone cellen. Zorg ervoor dat u opmaak toepast na het samenvoegen van cellen om de wijzigingen weerspiegeld te zien.

### 4. Is het mogelijk om de tabelindeling dynamisch aan te passen?

Ja, u kunt de tabelindeling dynamisch aanpassen door de celgroottes, tabelbreedte en andere eigenschappen te wijzigen op basis van de inhoud of de invoer van de gebruiker.

### 5. Waar kan ik meer informatie krijgen over tabelopmaak?

 Voor meer gedetailleerde voorbeelden en opties, bezoek de[Aspose.Words API-documentatie](https://reference.aspose.com/words/java/).