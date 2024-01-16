---
title: Inhoud toevoegen met DocumentBuilder in Aspose.Words voor Java
linktitle: Inhoud toevoegen met DocumentBuilder
second_title: Aspose.Words Java-documentverwerkings-API
description: Masterdocumentcreatie met Aspose.Words voor Java. Een stapsgewijze handleiding voor het toevoegen van tekst, tabellen, afbeeldingen en meer. Maak moeiteloos prachtige Word-documenten.
type: docs
weight: 26
url: /nl/java/document-manipulation/adding-content-using-documentbuilder/
---

## Inleiding tot het toevoegen van inhoud met behulp van DocumentBuilder in Aspose.Words voor Java

In deze stapsgewijze handleiding onderzoeken we hoe u Aspose.Words voor Java's DocumentBuilder kunt gebruiken om verschillende soorten inhoud aan een Word-document toe te voegen. We behandelen het invoegen van tekst, tabellen, horizontale regels, formuliervelden, HTML, hyperlinks, inhoudsopgave, inline en zwevende afbeeldingen, alinea's en meer. Laten we beginnen!

## Vereisten

 Voordat u begint, moet u ervoor zorgen dat de Aspose.Words voor Java-bibliotheek in uw project is ingesteld. Je kunt het downloaden van[hier](https://releases.aspose.com/words/java/).

## Tekst toevoegen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een eenvoudige tekstparagraaf in
builder.write("This is a simple text paragraph.");

// Bewaar het document
doc.save("path/to/your/document.docx");
```

## Tabellen toevoegen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Begin een tafel
Table table = builder.startTable();

// Voeg cellen en inhoud in
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// Beëindig de tafel
builder.endTable();

// Bewaar het document
doc.save("path/to/your/document.docx");
```

## Horizontale regel toevoegen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een horizontale regel in
builder.insertHorizontalRule();

// Bewaar het document
doc.save("path/to/your/document.docx");
```

## Formuliervelden toevoegen

### Veld voor tekstinvoerformulier

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een tekstinvoerformulierveld in
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// Bewaar het document
doc.save("path/to/your/document.docx");
```

### Selectievakje formulierveld

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een formulierveld voor een selectievakje in
builder.insertCheckBox("CheckBox", true, true, 0);

// Bewaar het document
doc.save("path/to/your/document.docx");
```

### Formulierveld met invoervak

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Definieer items voor de keuzelijst met invoervak
String[] items = { "Option 1", "Option 2", "Option 3" };

// Voeg een formulierveld met keuzelijst met invoervak in
builder.insertComboBox("DropDown", items, 0);

// Bewaar het document
doc.save("path/to/your/document.docx");
```

## HTML toevoegen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// HTML-inhoud invoegen
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// Bewaar het document
doc.save("path/to/your/document.docx");
```

## Hyperlinks toevoegen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een hyperlink in
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com", false);
builder.getFont().clearFormatting();
builder.write(" for more information.");

// Bewaar het document
doc.save("path/to/your/document.docx");
```

## Een inhoudsopgave toevoegen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een inhoudsopgave in
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Documentinhoud toevoegen
// ...

// Werk de inhoudsopgave bij
doc.updateFields();

// Bewaar het document
doc.save("path/to/your/document.docx");
```

## Afbeeldingen toevoegen

### Inline-afbeelding

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een inlineafbeelding in
builder.insertImage("path/to/your/image.png");

// Bewaar het document
doc.save("path/to/your/document.docx");
```

### Zwevend beeld

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een zwevende afbeelding in
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// Bewaar het document
doc.save("path/to/your/document.docx");
```

## Alinea's toevoegen

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Alinea-opmaak instellen
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Voeg een alinea in
builder.writeln("This is a formatted paragraph.");

// Bewaar het document
doc.save("path/to/your/document.docx");
```

## Stap 10: De cursor verplaatsen

 U kunt de cursorpositie binnen het document op verschillende manieren bepalen, zoals`moveToParagraph`, `moveToCell`en meer. Hier is een voorbeeld:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Verplaats de cursor naar een specifieke paragraaf
builder.moveToParagraph(2, 0);

// Voeg inhoud toe op de nieuwe cursorpositie
builder.writeln("This is the 3rd paragraph.");
```

Dit zijn enkele algemene bewerkingen die u kunt uitvoeren met Aspose.Words voor Java's DocumentBuilder. Verken de documentatie van de bibliotheek voor meer geavanceerde functies en aanpassingsopties. Veel succes met het maken van documenten!


## Conclusie

In deze uitgebreide handleiding hebben we de mogelijkheden van Aspose.Words voor Java's DocumentBuilder onderzocht om verschillende soorten inhoud aan Word-documenten toe te voegen. We hebben tekst, tabellen, horizontale regels, formuliervelden, HTML, hyperlinks, inhoudsopgave, afbeeldingen, alinea's en cursorbeweging behandeld.

## Veelgestelde vragen

### Vraag: Wat is Aspose.Words voor Java?

A: Aspose.Words voor Java is een Java-bibliotheek waarmee ontwikkelaars Microsoft Word-documenten programmatisch kunnen maken, wijzigen en manipuleren. Het biedt een breed scala aan functies voor het genereren, formatteren en invoegen van inhoud.

### Vraag: Hoe kan ik een inhoudsopgave aan mijn document toevoegen?

A: Om een inhoudsopgave toe te voegen, gebruikt u de`DocumentBuilder` om een inhoudsopgaveveld in uw document in te voegen. Zorg ervoor dat u de velden in het document bijwerkt nadat u inhoud hebt toegevoegd om de inhoudsopgave te vullen. Hier is een voorbeeld:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een inhoudsopgaveveld in
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Documentinhoud toevoegen
// ...

// Werk de inhoudsopgave bij
doc.updateFields();
```

### Vraag: Hoe voeg ik afbeeldingen in een document in met Aspose.Words voor Java?

 A: U kunt afbeeldingen invoegen, zowel inline als zwevend, met behulp van de`DocumentBuilder`. Hier zijn voorbeelden van beide:

#### Inline-afbeelding:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een inlineafbeelding in
builder.insertImage("path/to/your/image.png");
```

#### Zwevende afbeelding:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een zwevende afbeelding in
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### Vraag: Kan ik tekst en alinea's opmaken wanneer ik inhoud toevoeg?

 A: Ja, u kunt tekst en alinea's opmaken met behulp van de`DocumentBuilder`. U kunt lettertype-eigenschappen, alinea-uitlijning, inspringing en meer instellen. Hier is een voorbeeld:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Stel het lettertype en de alineaopmaak in
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Voeg een opgemaakte alinea in
builder.writeln("This is a formatted paragraph.");
```

### Vraag: Hoe kan ik de cursor naar een specifieke locatie in het document verplaatsen?

 A: U kunt de cursorpositie besturen met behulp van methoden zoals`moveToParagraph`, `moveToCell`en meer. Hier is een voorbeeld:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Verplaats de cursor naar een specifieke paragraaf
builder.moveToParagraph(2, 0);

// Voeg inhoud toe op de nieuwe cursorpositie
builder.writeln("This is the 3rd paragraph.");
```

Dit zijn enkele veelgestelde vragen en antwoorden om u op weg te helpen met Aspose.Words voor Java's DocumentBuilder. Als u meer vragen heeft of verdere hulp nodig heeft, raadpleegt u de[documentatie van de bibliotheek](https://reference.aspose.com/words/java/) of zoek hulp bij de Aspose.Words-gemeenschap en ondersteunende bronnen.