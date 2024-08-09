---
title: Hulpmethoden voor het extraheren van inhoud in Aspose.Words voor Java
linktitle: Hulpmethoden voor het extraheren van inhoud
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u inhoud efficiënt uit Word-documenten kunt extraheren met Aspose.Words voor Java. Ontdek hulpmethoden, aangepaste opmaak en meer in deze uitgebreide handleiding.
type: docs
weight: 14
url: /nl/java/document-manipulation/helper-methods-for-extracting-content/
---

## Inleiding tot helpermethoden voor het extraheren van inhoud in Aspose.Words voor Java

Aspose.Words voor Java is een krachtige bibliotheek waarmee ontwikkelaars programmatisch met Word-documenten kunnen werken. Een veel voorkomende taak bij het werken met Word-documenten is het extraheren van inhoud daaruit. In dit artikel zullen we enkele hulpmethoden verkennen voor het efficiënt extraheren van inhoud met behulp van Aspose.Words voor Java.

## Vereisten

Voordat we ingaan op de codevoorbeelden, moet u ervoor zorgen dat Aspose.Words voor Java is geïnstalleerd en ingesteld in uw Java-project. Je kunt het downloaden van[hier](https://releases.aspose.com/words/java/).

## Hulpmethode 1: Alinea's extraheren op stijl

```java
public static ArrayList<Paragraph> paragraphsByStyleName(Document doc, String styleName) {
    // Maak een array om alinea's van de opgegeven stijl te verzamelen.
    ArrayList<Paragraph> paragraphsWithStyle = new ArrayList<Paragraph>();
    NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);

    // Blader door alle alinea's om de alinea's met de opgegeven stijl te vinden.
    for (Paragraph paragraph : (Iterable<Paragraph>) paragraphs) {
        if (paragraph.getParagraphFormat().getStyle().getName().equals(styleName))
            paragraphsWithStyle.add(paragraph);
    }
    return paragraphsWithStyle;
}
```

U kunt deze methode gebruiken om alinea's met een specifieke stijl uit uw Word-document te extraheren. Dit is handig als u inhoud met een bepaalde opmaak wilt extraheren, zoals koppen of blokcitaten.

## Helpermethode 2: inhoud extraheren via knooppunten

```java
public static ArrayList<Node> extractContentBetweenNodes(Node startNode, Node endNode, boolean isInclusive) {
    // Controleer eerst of de knooppunten die aan deze methode worden doorgegeven, geldig zijn voor gebruik.
    verifyParameterNodes(startNode, endNode);
    
    // Maak een lijst om de geëxtraheerde knooppunten op te slaan.
    ArrayList<Node> nodes = new ArrayList<Node>();

    // Als een van beide markeringen deel uitmaakt van een opmerking, inclusief de opmerking zelf, moeten we de aanwijzer verplaatsen
    // doorsturen naar het Comment Node dat na het CommentRangeEnd-knooppunt wordt gevonden.
    if (endNode.getNodeType() == NodeType.COMMENT_RANGE_END && isInclusive) {
        Node node = findNextNode(NodeType.COMMENT, endNode.getNextSibling());
        if (node != null)
            endNode = node;
    }
    
    // Houd een overzicht bij van de oorspronkelijke knooppunten die aan deze methode zijn doorgegeven om indien nodig markeringsknooppunten te splitsen.
    Node originalStartNode = startNode;
    Node originalEndNode = endNode;

    //Extraheer inhoud op basis van knooppunten op blokniveau (paragrafen en tabellen). Doorloop de bovenliggende knooppunten om ze te vinden.
    // We zullen de inhoud van de eerste en laatste knooppunten splitsen, afhankelijk van of de markeringsknooppunten inline zijn.
    startNode = getAncestorInBody(startNode);
    endNode = getAncestorInBody(endNode);
    boolean isExtracting = true;
    boolean isStartingNode = true;
    // Het huidige knooppunt dat we uit het document halen.
    Node currNode = startNode;

    // Begin met het extraheren van inhoud. Verwerk alle knooppunten op blokniveau en splits specifiek de eerste
    // en laatste knooppunten indien nodig, zodat de alineaopmaak behouden blijft.
    // Deze methode is iets ingewikkelder dan een gewone extractor, omdat we er rekening mee moeten houden
    // bij het extraheren met behulp van inline knooppunten, velden, bladwijzers, enz., om het nuttig te maken.
    while (isExtracting) {
        // Kloon het huidige knooppunt en de onderliggende knooppunten om een kopie te verkrijgen.
        Node cloneNode = currNode.deepClone(true);
        boolean isEndingNode = currNode.equals(endNode);
        if (isStartingNode || isEndingNode) {
            // We moeten elke marker afzonderlijk verwerken, dus geef deze in plaats daarvan door aan een aparte methode.
            // End moet eerst worden verwerkt om de knooppuntindexen te behouden.
            if (isEndingNode) {
                // !isStartingNode: voeg het knooppunt niet tweemaal toe als de markeringen hetzelfde knooppunt zijn.
                processMarker(cloneNode, nodes, originalEndNode, currNode, isInclusive,
                        false, !isStartingNode, false);
                isExtracting = false;
            }
            //Voorwaardelijk moet gescheiden zijn, omdat de start- en eindmarkeringen op blokniveau hetzelfde knooppunt kunnen zijn.
            if (isStartingNode) {
                processMarker(cloneNode, nodes, originalStartNode, currNode, isInclusive,
                        true, true, false);
                isStartingNode = false;
            }
        } else
            // Knooppunt is geen begin- of eindmarkering; voeg eenvoudigweg de kopie toe aan de lijst.
            nodes.add(cloneNode);

        // Ga naar het volgende knooppunt en pak het uit. Als het volgende knooppunt nul is,
        // de rest van de inhoud is te vinden in een andere sectie.
        if (currNode.getNextSibling() == null && isExtracting) {
            // Ga naar de volgende sectie.
            Section nextSection = (Section) currNode.getAncestor(NodeType.SECTION).getNextSibling();
            currNode = nextSection.getBody().getFirstChild();
        } else {
            // Ga naar het volgende knooppunt in het lichaam.
            currNode = currNode.getNextSibling();
        }
    }

    // Voor compatibiliteit met de modus met inline bladwijzers voegt u de volgende alinea (leeg) toe.
    if (isInclusive && originalEndNode == endNode && !originalEndNode.isComposite())
        includeNextParagraph(endNode, nodes);

    // Retourneer de knooppunten tussen de knooppuntmarkeringen.
    return nodes;
}
```

Met deze methode kunt u inhoud extraheren tussen twee gespecificeerde knooppunten, of dit nu alinea's, tabellen of andere elementen op blokniveau zijn. Het verwerkt verschillende scenario's, waaronder inline markeringen, velden en bladwijzers.

## Helpermethode 3: Een nieuw document genereren

```java
public static Document generateDocument(Document srcDoc, ArrayList<Node> nodes) throws Exception {
    Document dstDoc = new Document();
    
    // Verwijder de eerste alinea uit het lege document.
    dstDoc.getFirstSection().getBody().removeAllChildren();
    
    // Importeer elk knooppunt uit de lijst in het nieuwe document. Behoud de oorspronkelijke opmaak van het knooppunt.
    NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
    for (Node node : nodes) {
        Node importNode = importer.importNode(node, true);
        dstDoc.getFirstSection().getBody().appendChild(importNode);
    }
    
    return dstDoc;
}
```

Met deze methode kunt u een nieuw document genereren door een lijst met knooppunten uit het brondocument te importeren. Het behoudt de oorspronkelijke opmaak van de knooppunten, waardoor het handig is voor het maken van nieuwe documenten met specifieke inhoud.

## Conclusie

Het extraheren van inhoud uit Word-documenten kan een cruciaal onderdeel zijn van veel documentverwerkingstaken. Aspose.Words voor Java biedt krachtige hulpmethoden die dit proces vereenvoudigen. Of u nu alinea's moet extraheren op stijl, inhoud tussen knooppunten, of nieuwe documenten moet genereren, deze methoden helpen u efficiënt te werken met Word-documenten in uw Java-toepassingen.

## Veelgestelde vragen

### Hoe kan ik Aspose.Words voor Java installeren?

 Om Aspose.Words voor Java te installeren, kunt u het downloaden van de Aspose-website. Bezoek[hier](https://releases.aspose.com/words/java/) om de nieuwste versie te krijgen.

### Kan ik inhoud uit specifieke secties van een Word-document extraheren?

Ja, u kunt inhoud uit specifieke secties van een Word-document extraheren met behulp van de methoden die in dit artikel worden vermeld. Geef eenvoudigweg de begin- en eindknooppunten op die de sectie definiëren die u wilt extraheren.

### Is Aspose.Words voor Java compatibel met Java 11?

Ja, Aspose.Words voor Java is compatibel met Java 11 en hogere versies. U kunt het zonder problemen in uw Java-toepassingen gebruiken.

### Kan ik de opmaak van de geëxtraheerde inhoud aanpassen?

Ja, u kunt de opmaak van de geëxtraheerde inhoud aanpassen door de geïmporteerde knooppunten in het gegenereerde document te wijzigen. Aspose.Words voor Java biedt uitgebreide opmaakopties om aan uw behoeften te voldoen.

### Waar kan ik meer documentatie en voorbeelden vinden voor Aspose.Words voor Java?

 Uitgebreide documentatie en voorbeelden voor Aspose.Words voor Java vindt u op de Aspose-website. Bezoek[https://reference.aspose.com/words/java/](https://reference.aspose.com/words/java/) voor gedetailleerde documentatie en bronnen.