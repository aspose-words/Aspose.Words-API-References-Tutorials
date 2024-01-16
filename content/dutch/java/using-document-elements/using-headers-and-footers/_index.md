---
title: Kop- en voetteksten gebruiken in Aspose.Words voor Java
linktitle: Kop- en voetteksten gebruiken
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer stap voor stap hoe u kop- en voetteksten gebruikt in Aspose.Words voor Java. Creëer moeiteloos professionele documenten.
type: docs
weight: 16
url: /nl/java/using-document-elements/using-headers-and-footers/
---

In deze uitgebreide handleiding leiden we u door het proces van het werken met kop- en voetteksten in Aspose.Words voor Java. Kop- en voetteksten zijn essentiële elementen bij de documentopmaak, en Aspose.Words biedt krachtige hulpmiddelen om deze te maken en aan te passen aan uw behoeften.

Laten we nu eens in detail op elk van deze stappen ingaan.

## 1. Inleiding tot Aspose.Words

Aspose.Words is een krachtige Java API waarmee u Word-documenten programmatisch kunt maken, manipuleren en weergeven. Het biedt uitgebreide functies voor documentopmaak, inclusief kop- en voetteksten.

## 2. Uw Java-omgeving instellen

 Voordat u Aspose.Words gaat gebruiken, moet u ervoor zorgen dat uw Java-ontwikkelomgeving correct is ingesteld. U kunt de benodigde installatie-instructies vinden op de documentatiepagina van Aspose.Words:[Aspose.Words Java-documentatie](https://reference.aspose.com/words/java/).

## 3. Een nieuw document maken

Als u met kop- en voetteksten wilt werken, moet u een nieuw document maken met Aspose.Words. De volgende code laat zien hoe u dit doet:

```java
// Java-code voor het maken van een nieuw document
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. Pagina-instelling begrijpen

 Pagina-instelling is cruciaal voor het bepalen van de lay-out van uw document. U kunt verschillende eigenschappen met betrekking tot kop- en voetteksten opgeven met behulp van de`PageSetup` klas. Bijvoorbeeld:

```java
// Pagina-eigenschappen instellen
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. Andere koptekst/voettekst van de eerste pagina

Met Aspose.Words kunt u verschillende kop- en voetteksten hebben voor de eerste pagina van uw document. Gebruik`pageSetup.setDifferentFirstPageHeaderFooter(true);` om deze functie in te schakelen.

## 6. Werken met kopteksten

### 6.1. Tekst aan kopteksten toevoegen

 U kunt tekst aan kopteksten toevoegen met behulp van de`DocumentBuilder`. Hier is een voorbeeld:

```java
// Tekst toevoegen aan de koptekst van de eerste pagina
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. Afbeeldingen in headers invoegen

 Om afbeeldingen in headers in te voegen, kunt u de`insertImage` methode. Hier is een voorbeeld:

```java
// Een afbeelding in de koptekst invoegen
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. Koptekststijlen aanpassen

U kunt koptekststijlen aanpassen door verschillende eigenschappen in te stellen, zoals lettertype, uitlijning en meer, zoals weergegeven in de bovenstaande voorbeelden.

## 7. Werken met voetteksten

### 7.1. Tekst toevoegen aan voetteksten

 Net als bij kopteksten kunt u tekst aan voetteksten toevoegen met behulp van de`DocumentBuilder`. Hier is een voorbeeld:

```java
// Tekst toevoegen aan de primaire voettekst
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// Voeg indien nodig tekst en velden in
```

### 7.2. Afbeeldingen in voetteksten invoegen

 Om afbeeldingen in voetteksten in te voegen, gebruikt u de`insertImage` methode, net als in headers.

### 7.3. Voettekststijlen aanpassen

 Pas voettekststijlen aan met behulp van de`DocumentBuilder`vergelijkbaar met het aanpassen van headers.

## 8. Paginanummering

 U kunt paginanummers opnemen in uw kop- en voetteksten met behulp van velden als`PAGE` En`NUMPAGES`. Deze velden worden automatisch bijgewerkt wanneer u pagina's toevoegt of verwijdert.

## 9. Copyrightinformatie in voetteksten

Als u copyrightinformatie aan de voettekst van uw document wilt toevoegen, kunt u een tabel met twee cellen gebruiken, waarbij u de ene links en de andere rechts uitlijnt, zoals weergegeven in het codefragment.

## 10. Werken met meerdere secties

Met Aspose.Words kunt u met meerdere secties binnen een document werken. U kunt voor elke sectie verschillende pagina-instellingen en kop-/voetteksten instellen.

## 11. Landschapsoriëntatie

U kunt indien nodig de richting van specifieke secties wijzigen in de liggende modus.

## 12. Kop- en voetteksten uit eerdere secties kopiëren

Het kopiëren van kop- en voetteksten uit eerdere secties kan tijd besparen bij het maken van complexe documenten.

## 13. Uw document opslaan

Nadat u uw document hebt gemaakt en aangepast, vergeet dan niet om het op te slaan met behulp van de`doc.save()` methode.

## Volledige broncode
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // Geef op of we willen dat de kop- en voetteksten van de eerste pagina verschillen van andere pagina's.
        // U kunt ook de eigenschap PageSetup.OddAndEvenPagesHeaderFooter gebruiken om op te geven
        // verschillende kop-/voetteksten voor oneven en even pagina's.
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // Voeg een gepositioneerde afbeelding in de linkerbovenhoek van de koptekst in.
        // De afstand vanaf de boven-/linkerrand van de pagina is ingesteld op 10 punten.
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // We gebruiken een tabel met twee cellen om één deel van de tekst op de regel te zetten (met paginanummering).
        // Moet links uitgelijnd worden, en het overige deel van de tekst (met copyright) moet rechts uitgelijnd worden.
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // Het gebruikt de velden PAGE en NUMPAGES om automatisch het huidige paginanummer en vele pagina's te berekenen.
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // Maak een pagina-einde om een tweede pagina te maken waarop de primaire kop-/voetteksten te zien zijn.
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // Deze sectie heeft geen andere kop-/voettekst op de eerste pagina nodig. We hebben slechts één titelpagina in het document nodig.
        //en de kop-/voettekst voor deze pagina is al gedefinieerd in de vorige sectie.
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // In deze sectie worden kop- en voetteksten uit de vorige sectie weergegeven
        // Roep standaard currentSection.HeadersFooters.LinkToPrevious(false) aan om deze paginabreedte te annuleren
        // is anders voor de nieuwe sectie, en daarom moeten we verschillende celbreedtes instellen voor een voetteksttabel.
        currentSection.getHeadersFooters().linkToPrevious(false);
        // Als we de reeds bestaande kop-/voettekstset voor deze sectie willen gebruiken.
        // Maar met enkele kleine aanpassingen kan het handig zijn om kop- en voetteksten te kopiëren
        // uit de vorige sectie en pas de nodige wijzigingen toe waar we ze willen hebben.
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
Broncode van de methode copyHeadersFootersFromPreviousSection
```java
    /// <samenvatting>
    /// Klonen en kop-/voetteksten kopiëren van de vorige sectie naar de opgegeven sectie.
    ///</samenvatting>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## Conclusie

In deze zelfstudie hebben we de basisbeginselen besproken van het werken met kop- en voetteksten in Aspose.Words voor Java. U hebt geleerd hoe u kop- en voetteksten kunt maken, aanpassen en vormgeven, evenals andere essentiële technieken voor documentopmaak.

 Voor meer details en geavanceerde functies raadpleegt u de[Aspose.Words Java-documentatie](https://reference.aspose.com/words/java/).

## Veelgestelde vragen

### 1. Hoe kan ik paginanummers toevoegen aan de voettekst van mijn document?
 U kunt paginanummers toevoegen door de`PAGE` veld in de voettekst met Aspose.Words.

### 2. Is Aspose.Words compatibel met Java-ontwikkelomgevingen?
Ja, Aspose.Words biedt ondersteuning voor Java-ontwikkeling. Zorg ervoor dat u over de benodigde instellingen beschikt.

### 3. Kan ik het lettertype en de stijl van kop- en voetteksten aanpassen?
Absoluut, u kunt lettertypen, uitlijning en andere stijlen aanpassen om uw kop- en voetteksten visueel aantrekkelijk te maken.

### 4. Is het mogelijk om verschillende headers te hebben voor oneven en even pagina's?
 Ja, je kunt het gebruiken`PageSetup.OddAndEvenPagesHeaderFooter` om verschillende kopteksten voor oneven en even pagina's op te geven.

### 5. Hoe ga ik aan de slag met Aspose.Words voor Java?
 Bezoek om te beginnen de[Aspose.Words Java-documentatie](https://reference.aspose.com/words/java/) voor uitgebreide richtlijnen voor het gebruik van de API.