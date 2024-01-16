---
title: Tekst zoeken en vervangen in Aspose.Words voor Java
linktitle: Tekst zoeken en vervangen
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u tekst in Word-documenten kunt zoeken en vervangen met Aspose.Words voor Java. Stapsgewijze handleiding met codevoorbeelden. Verbeter uw vaardigheden op het gebied van Java-documentmanipulatie.
type: docs
weight: 15
url: /nl/java/document-manipulation/finding-and-replacing-text/
---

## Inleiding tot het zoeken en vervangen van tekst in Aspose.Words voor Java

Aspose.Words voor Java is een krachtige Java API waarmee u programmatisch met Word-documenten kunt werken. Een van de meest voorkomende taken bij het werken met Word-documenten is het zoeken en vervangen van tekst. Of u nu tijdelijke aanduidingen in sjablonen moet bijwerken of complexere tekstmanipulaties moet uitvoeren, Aspose.Words voor Java kan u helpen uw doelen efficiënt te bereiken.

## Vereisten

Voordat we dieper ingaan op de details van het zoeken en vervangen van tekst, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java-ontwikkelomgeving
- Aspose.Words voor Java-bibliotheek
- Een voorbeeld van een Word-document om mee te werken

 U kunt de Aspose.Words voor Java-bibliotheek downloaden van[hier](https://releases.aspose.com/words/java/).

## Eenvoudige tekst zoeken en vervangen

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Maak een DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Tekst zoeken en vervangen
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

 In dit voorbeeld laden we een Word-document, maken we een`DocumentBuilder` en gebruik de`replace` methode om "oude tekst" te vinden en te vervangen door "nieuwe tekst" in het document.

## Reguliere expressies gebruiken

Reguliere expressies bieden krachtige mogelijkheden voor patroonvergelijking voor het zoeken en vervangen van tekst. Aspose.Words voor Java ondersteunt reguliere expressies voor geavanceerdere zoek- en vervangbewerkingen.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Maak een DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Gebruik reguliere expressies voor het zoeken en vervangen van tekst
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

In dit voorbeeld gebruiken we een reguliere-expressiepatroon om tekst in het document te zoeken en te vervangen.

## Tekst in velden negeren

kunt Aspose.Words configureren om tekst in velden te negeren bij het uitvoeren van zoek- en vervangbewerkingen.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Maak een FindReplaceOptions-instantie en stel IgnoreFields in op true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Gebruik opties bij het vervangen van tekst
doc.getRange().replace("text-to-replace", "new-text", options);

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

Dit is handig als u wilt uitsluiten dat tekst in velden, zoals samenvoegvelden, wordt vervangen.

## Tekst binnenin negeren Revisies verwijderen

U kunt Aspose.Words configureren om tekst in verwijderrevisies te negeren tijdens zoek- en vervangbewerkingen.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Maak een FindReplaceOptions-instantie en stel IgnoreDeleted in op true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Gebruik opties bij het vervangen van tekst
doc.getRange().replace("text-to-replace", "new-text", options);

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

Hiermee kunt u uitsluiten dat tekst die is gemarkeerd voor verwijdering in bijgehouden wijzigingen, wordt vervangen.

## Tekst in invoegrevisies negeren

U kunt Aspose.Words configureren om tekst in invoegrevisies te negeren tijdens zoek- en vervangbewerkingen.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Maak een FindReplaceOptions-instantie en stel IgnoreInserted in op true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Gebruik opties bij het vervangen van tekst
doc.getRange().replace("text-to-replace", "new-text", options);

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

Hierdoor kunt u uitsluiten dat tekst die is gemarkeerd als ingevoegd in bijgehouden wijzigingen, wordt vervangen.

## Tekst vervangen door HTML

U kunt Aspose.Words voor Java gebruiken om tekst te vervangen door HTML-inhoud.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Maak een FindReplaceOptions-instantie met een aangepaste vervangende callback
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Gebruik opties bij het vervangen van tekst
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

 In dit voorbeeld gebruiken we een custom`ReplaceWithHtmlEvaluator` om tekst te vervangen door HTML-inhoud.

## Tekst in kop- en voetteksten vervangen

U kunt tekst zoeken en vervangen in de kop- en voetteksten van uw Word-document.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Verkrijg de verzameling kop- en voetteksten
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Kies het kop- of voetteksttype waarin u tekst wilt vervangen (bijvoorbeeld HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// Maak een FindReplaceOptions-instantie en pas deze toe op het bereik van de voettekst
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

Hierdoor kunt u tekstvervangingen specifiek in kop- en voetteksten uitvoeren.

## Wijzigingen voor kop- en voettekstorders weergeven

U kunt Aspose.Words gebruiken om wijzigingen in de kop- en voettekstvolgorde in uw document weer te geven.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Haal het eerste gedeelte
Section firstPageSection = doc.getFirstSection();

// Maak een FindReplaceOptions-instantie en pas deze toe op het bereik van het document
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//Vervang tekst die van invloed is op de kop- en voettekstvolgorde
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

Hierdoor kunt u wijzigingen met betrekking tot de kop- en voettekstvolgorde in uw document visualiseren.

## Tekst vervangen door velden

U kunt tekst vervangen door velden met Aspose.Words voor Java.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Maak een FindReplaceOptions-instantie en stel een aangepaste vervangende callback voor velden in
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Gebruik opties bij het vervangen van tekst
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

 In dit voorbeeld vervangen we tekst door velden en specificeren we het veldtype (bijv.`FieldType.FIELD_MERGE_FIELD`).

## Vervangen door een Evaluator

U kunt een aangepaste evaluator gebruiken om de vervangende tekst dynamisch te bepalen.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Maak een FindReplaceOptions-instantie en stel een aangepaste vervangende callback in
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Gebruik opties bij het vervangen van tekst
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

In dit voorbeeld gebruiken we een aangepaste evaluator (`MyReplaceEvaluator`) om tekst te vervangen.

## Vervangen door Regex

Met Aspose.Words voor Java kunt u tekst vervangen door reguliere expressies.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Gebruik reguliere expressies voor het zoeken en vervangen van tekst
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

In dit voorbeeld gebruiken we een reguliere-expressiepatroon om tekst in het document te zoeken en te vervangen.

## Herkennen en vervangingen binnen vervangingspatronen

Met Aspose.Words voor Java kunt u vervangingen binnen vervangingspatronen herkennen en uitvoeren.

```java
// Laad het document
Document doc = new Document("your-document.docx");

//Maak een FindReplaceOptions-instantie waarbij UseSubstitutions is ingesteld op true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Gebruik opties wanneer u tekst vervangt door een patroon
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

Hierdoor kunt u vervangingen uitvoeren binnen de vervangingspatronen voor meer geavanceerde vervangingen.

## Vervangen door een string

U kunt tekst vervangen door een eenvoudige tekenreeks met Aspose.Words voor Java.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Vervang tekst door een tekenreeks
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

In dit voorbeeld vervangen we "text-to-replace" door "new-string" in het document.

## Legacy-bestelling gebruiken

U kunt een verouderde volgorde gebruiken bij het uitvoeren van zoek- en vervangbewerkingen.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Maak een FindReplaceOptions-instantie en stel UseLegacyOrder in op true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Gebruik opties bij het vervangen van tekst
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

Hierdoor kunt u de verouderde volgorde gebruiken voor zoek- en vervangbewerkingen.

## Tekst in een tabel vervangen

U kunt tekst in tabellen in uw Word-document zoeken en vervangen.

```java
// Laad het document
Document doc = new Document("your-document.docx");

// Een specifieke tafel ophalen (bijvoorbeeld de eerste tafel)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// Gebruik FindReplaceOptions voor het vervangen van tekst in de tabel
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Sla het gewijzigde document op
doc.save("modified-document.docx");
```

Hierdoor kunt u specifiek binnen tabellen tekstvervangingen uitvoeren.

## Conclusie

Aspose.Words voor Java biedt uitgebreide mogelijkheden voor het vinden en vervangen van tekst in Word-documenten. Of u nu eenvoudige tekstvervangingen of meer geavanceerde bewerkingen moet uitvoeren met behulp van reguliere expressies, veldmanipulaties of aangepaste evaluatieprogramma's, Aspose.Words voor Java heeft de oplossing voor u. Zorg ervoor dat u de uitgebreide documentatie en voorbeelden van Aspose verkent om het volledige potentieel van deze krachtige Java-bibliotheek te benutten.

## Veelgestelde vragen

### Hoe download ik Aspose.Words voor Java?

 U kunt Aspose.Words voor Java downloaden van de website door naar[deze link](https://releases.aspose.com/words/java/).

### Kan ik reguliere expressies gebruiken voor tekstvervanging?

Ja, u kunt reguliere expressies gebruiken voor tekstvervanging in Aspose.Words voor Java. Hierdoor kunt u geavanceerdere en flexibelere zoek- en vervangbewerkingen uitvoeren.

### Hoe kan ik tekst in velden negeren tijdens het vervangen?

 Om tekst in velden te negeren tijdens het vervangen, kunt u de`IgnoreFields` eigendom van de`FindReplaceOptions` naar`true`Dit zorgt ervoor dat tekst binnen velden, zoals samenvoegvelden, wordt uitgesloten van de vervanging.

### Kan ik tekst in kop- en voetteksten vervangen?

 Ja, u kunt tekst in de kop- en voetteksten van uw Word-document vervangen. Ga eenvoudigweg naar de juiste kop- of voettekst en gebruik de`replace` methode met het gewenste`FindReplaceOptions`.

### Waar is de UseLegacyOrder-optie voor?

 De`UseLegacyOrder` optie in`FindReplaceOptions` Hiermee kunt u de oude volgorde gebruiken bij het uitvoeren van zoek- en vervangbewerkingen. Dit kan handig zijn in bepaalde scenario's waarin verouderd ordergedrag gewenst is.