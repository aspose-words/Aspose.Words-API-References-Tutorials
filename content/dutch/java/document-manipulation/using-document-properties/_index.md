---
title: Documenteigenschappen gebruiken in Aspose.Words voor Java
linktitle: Documenteigenschappen gebruiken
second_title: Aspose.Words Java-documentverwerkings-API
description: Optimaliseer documentbeheer met Aspose.Words voor Java. Leer werken met documenteigenschappen, voeg aangepaste metagegevens toe en meer in deze uitgebreide zelfstudie.
type: docs
weight: 32
url: /nl/java/document-manipulation/using-document-properties/
---

## Inleiding tot documenteigenschappen

Documenteigenschappen zijn een essentieel onderdeel van elk document. Ze bieden aanvullende informatie over het document zelf, zoals de titel, auteur, onderwerp, trefwoorden en meer. In Aspose.Words voor Java kunt u zowel ingebouwde als aangepaste documenteigenschappen manipuleren.

## Documenteigenschappen opsommen

### Ingebouwde eigenschappen

Om ingebouwde documenteigenschappen op te halen en ermee te werken, kunt u het volgende codefragment gebruiken:

```java
@Test
public void enumerateProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
    System.out.println("2. Built-in Properties");
    for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
        System.out.println(MessageFormat.format("{0} : {1}", prop.getName(), prop.getValue()));
}
```

Deze code geeft de naam van het document en de ingebouwde eigenschappen weer, inclusief eigenschappen als 'Titel', 'Auteur' en 'Trefwoorden'.

### Aangepaste eigenschappen

Als u met aangepaste documenteigenschappen wilt werken, kunt u het volgende codefragment gebruiken:

```java
@Test
public void addCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();

    if (customDocumentProperties.get("Authorized") != null) return;

    customDocumentProperties.add("Authorized", true);
    customDocumentProperties.add("Authorized By", "John Smith");
    customDocumentProperties.add("Authorized Date", new Date());
    customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
    customDocumentProperties.add("Authorized Amount", 123.45);
}
```

Dit codefragment laat zien hoe u aangepaste documenteigenschappen kunt toevoegen, waaronder een Booleaanse waarde, een tekenreeks, een datum, een revisienummer en een numerieke waarde.

## Documenteigenschappen verwijderen

Om specifieke documenteigenschappen te verwijderen, kunt u de volgende code gebruiken:

```java
@Test
public void removeCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    doc.getCustomDocumentProperties().remove("Authorized Date");
}
```

Deze code verwijdert de aangepaste eigenschap 'Geautoriseerde datum' uit het document.

## Link naar inhoud configureren

In sommige gevallen wilt u mogelijk koppelingen in uw document maken. Hier ziet u hoe u het kunt doen:

```java
@Test
public void configuringLinkToContent() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.startBookmark("MyBookmark");
    builder.writeln("Text inside a bookmark.");
    builder.endBookmark("MyBookmark");

    CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();

    // Voeg gekoppeld aan inhoudseigenschap toe.
    DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
    customProperty = customProperties.get("Bookmark");
    boolean isLinkedToContent = customProperty.isLinkToContent();
    String linkSource = customProperty.getLinkSource();
    String customPropertyValue = customProperty.getValue().toString();
}
```

Dit codefragment laat zien hoe u een bladwijzer in uw document kunt maken en een aangepaste documenteigenschap kunt toevoegen die naar die bladwijzer linkt.

## Converteren tussen meeteenheden

In Aspose.Words voor Java kunt u eenvoudig meeteenheden converteren. Hier is een voorbeeld van hoe u dit moet doen:

```java
@Test
public void convertBetweenMeasurementUnits() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    PageSetup pageSetup = builder.getPageSetup();

    // Stel de marges in inches in.
    pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
    pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
}
```

Met dit codefragment worden verschillende marges en afstanden in inches ingesteld door deze naar punten te converteren.

## Controletekens gebruiken

Controletekens kunnen handig zijn bij het omgaan met tekst. Zo vervangt u een controleteken in uw tekst:

```java
@Test
public void useControlCharacters()
{
    final String TEXT = "test\r";

    // Vervang het controleteken "\r" door "\r\n".
    String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
}
```

In dit voorbeeld vervangen we de regelterugloop (`\r`) met een harde return gevolgd door een regelinvoer (`\r\n`).

## Conclusie

Documenteigenschappen spelen een belangrijke rol bij het effectief beheren en organiseren van uw documenten in Aspose.Words voor Java. Of u nu werkt met ingebouwde eigenschappen, aangepaste eigenschappen of het gebruik van besturingstekens, u beschikt over een reeks hulpmiddelen om uw mogelijkheden voor documentbeheer te verbeteren.

## Veelgestelde vragen

### Hoe krijg ik toegang tot de ingebouwde documenteigenschappen?

 Om toegang te krijgen tot ingebouwde documenteigenschappen in Aspose.Words voor Java, kunt u de`getBuiltInDocumentProperties` methode op de`Document` voorwerp. Deze methode retourneert een verzameling ingebouwde eigenschappen die u kunt doorlopen.

### Kan ik aangepaste documenteigenschappen aan een document toevoegen?

 Ja, u kunt aangepaste documenteigenschappen aan een document toevoegen met behulp van de`CustomDocumentProperties` verzameling. U kunt aangepaste eigenschappen definiëren met verschillende gegevenstypen, waaronder tekenreeksen, booleaanse waarden, datums en numerieke waarden.

### Hoe kan ik een specifieke aangepaste documenteigenschap verwijderen?

 Om een specifieke aangepaste documenteigenschap te verwijderen, kunt u de`remove` methode op de`CustomDocumentProperties`collection, waarbij u de naam van de eigenschap die u wilt verwijderen als parameter doorgeeft.

### Wat is het doel van het linken naar inhoud in een document?

Door naar inhoud in een document te linken, kunt u dynamische verwijzingen naar specifieke delen van het document maken. Dit kan handig zijn voor het maken van interactieve documenten of kruisverwijzingen tussen secties.

### Hoe kan ik tussen verschillende maateenheden converteren in Aspose.Words voor Java?

 U kunt in Aspose.Words voor Java tussen verschillende maateenheden converteren met behulp van de`ConvertUtil` klas. Het biedt methoden om eenheden zoals inches naar punten, punten naar centimeters en meer te converteren.