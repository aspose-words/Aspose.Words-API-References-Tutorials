---
title: Inhoud verwijderen uit documenten in Aspose.Words voor Java
linktitle: Inhoud uit documenten verwijderen
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u inhoud uit Word-documenten in Java verwijdert met Aspose.Words voor Java. Verwijder pagina-einden, sectie-einden en meer. Optimaliseer uw documentverwerking.
type: docs
weight: 16
url: /nl/java/document-manipulation/removing-content-from-documents/
---

## Inleiding tot Aspose.Words voor Java

Voordat we dieper ingaan op de verwijderingstechnieken, stellen we Aspose.Words voor Java kort voor. Het is een Java API die uitgebreide functies biedt voor het werken met Word-documenten. Met deze bibliotheek kunt u naadloos Word-documenten maken, bewerken, converteren en manipuleren.

## Pagina-einden verwijderen

Pagina-einden worden vaak gebruikt om de lay-out van een document te bepalen. Er kunnen echter gevallen zijn waarin u ze moet verwijderen. Zo kunt u pagina-einden verwijderen met Aspose.Words voor Java:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);
for (Paragraph para : (Iterable<Paragraph>) paragraphs) {
    if (para.getParagraphFormat().getPageBreakBefore()) {
        para.getParagraphFormat().setPageBreakBefore(false);
    }
    for (Run run : para.getRuns()) {
        if (run.getText().contains(ControlChar.PAGE_BREAK)) {
            run.setText(run.getText().replace(ControlChar.PAGE_BREAK, ""));
        }
    }
}
doc.save("Your Directory Path" + "RemoveContent.RemovePageBreaks.docx");
```

Dit codefragment loopt door de paragrafen in het document, controleert op pagina-einden en verwijdert deze.

## Sectie-einden verwijderen

Sectie-einden verdelen een document in afzonderlijke secties met verschillende opmaak. Volg deze stappen om sectie-einden te verwijderen:

```java
for (int i = doc.getSections().getCount() - 2; i >= 0; i--) {
    doc.getLastSection().prependContent(doc.getSections().get(i));
    doc.getSections().get(i).remove();
}
```

Deze code doorloopt secties in omgekeerde volgorde, waarbij de inhoud van de huidige sectie wordt gecombineerd met de laatste en vervolgens de gekopieerde sectie wordt verwijderd.

## Voetteksten verwijderen

Voetteksten in Word-documenten bevatten vaak paginanummers, datums of andere informatie. Als u ze wilt verwijderen, kunt u de volgende code gebruiken:

```java
Document doc = new Document("Your Directory Path" + "Header and footer types.docx");
for (Section section : doc.getSections()) {
    HeaderFooter footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_FIRST);
    footer.remove();
    footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
    footer.remove();
    footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_EVEN);
    footer.remove();
}
doc.save("Your Directory Path" + "RemoveContent.RemoveFooters.docx");
```

Deze code verwijdert alle soorten voetteksten (eerste, primaire en even) uit elke sectie in het document.

## Inhoudsopgave verwijderen

Inhoudsopgavevelden (TOC) genereren een dynamische tabel met koppen en hun paginanummers. Om een inhoudsopgave te verwijderen, kunt u de volgende code gebruiken:

```java
Document doc = new Document("Your Directory Path" + "Table of contents.docx");
removeTableOfContents(doc, 0);
doc.save("Your Directory Path" + "RemoveContent.RemoveToc.doc");
```

 Deze code definieert een methode`removeTableOfContents` waarmee de opgegeven inhoudsopgave uit het document wordt verwijderd.


## Conclusie

In dit artikel hebben we onderzocht hoe u verschillende soorten inhoud uit Word-documenten kunt verwijderen met Aspose.Words voor Java. Of het nu gaat om pagina-einden, sectie-einden, voetteksten of inhoudsopgave, Aspose.Words biedt de hulpmiddelen om uw documenten effectief te manipuleren.

## Veelgestelde vragen

### Hoe kan ik specifieke pagina-einden verwijderen?

Om specifieke pagina-einden te verwijderen, loopt u door de alinea's in uw document en wist u het pagina-einde-attribuut voor de gewenste alinea's.

### Kan ik kopteksten samen met voetteksten verwijderen?

Ja, u kunt zowel kop- als voetteksten uit uw document verwijderen door een vergelijkbare aanpak te volgen als weergegeven in het artikel over voetteksten.

### Is Aspose.Words voor Java compatibel met de nieuwste Word-documentformaten?

Ja, Aspose.Words voor Java ondersteunt de nieuwste Word-documentformaten, waardoor compatibiliteit met moderne documenten wordt gegarandeerd.

### Welke andere functies voor documentmanipulatie biedt Aspose.Words voor Java?

Aspose.Words voor Java biedt een breed scala aan functies, waaronder het maken, bewerken, converteren en meer van documenten. U kunt de documentatie raadplegen voor gedetailleerde informatie.