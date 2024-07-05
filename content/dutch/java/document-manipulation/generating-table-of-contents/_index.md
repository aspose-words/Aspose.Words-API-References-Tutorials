---
title: Inhoudsopgave genereren in Aspose.Words voor Java
linktitle: Inhoudsopgave genereren
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u een inhoudsopgave (TOC) kunt genereren en aanpassen met Aspose.Words voor Java. Creëer moeiteloos georganiseerde en professionele documenten.
type: docs
weight: 21
url: /nl/java/document-manipulation/generating-table-of-contents/
---

## Inleiding tot het genereren van een inhoudsopgave in Aspose.Words voor Java

In deze zelfstudie begeleiden we u bij het genereren van een inhoudsopgave (TOC) met Aspose.Words voor Java. TOC is een cruciale functie voor het maken van georganiseerde documenten. We bespreken hoe u het uiterlijk en de lay-out van de inhoudsopgave kunt aanpassen.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat Aspose.Words voor Java is geïnstalleerd en ingesteld in uw Java-project.

## Stap 1: Maak een nieuw document

Laten we eerst een nieuw document maken om mee te werken.

```java
Document doc = new Document();
```

## Stap 2: TOC-stijlen aanpassen

Om het uiterlijk van uw inhoudsopgave aan te passen, kunt u de bijbehorende stijlen wijzigen. In dit voorbeeld maken we de inhoudsopgavegegevens van het eerste niveau vetgedrukt.

```java
doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_1).getFont().setBold(true);
```

## Stap 3: Voeg inhoud toe aan uw document

U kunt uw inhoud aan het document toevoegen. Deze inhoud wordt gebruikt om de inhoudsopgave te genereren.

## Stap 4: Genereer de inhoudsopgave

Om de inhoudsopgave te genereren, voegt u een inhoudsopgaveveld in op de gewenste locatie in uw document. Dit veld wordt automatisch ingevuld op basis van de koppen en stijlen in uw document.

```java
// Voeg een TOC-veld in op de gewenste locatie in uw document.
FieldToc fieldToc = new FieldToc();
doc.getFirstSection().getBody().getFirstParagraph().appendChild(fieldToc);
```

## Stap 5: Sla het document op

Sla ten slotte het document op met de inhoudsopgave.

```java
doc.save("your_output_path_here");
```

## Tabstops in inhoudsopgave aanpassen

U kunt ook de tabstops in uw inhoudsopgave aanpassen om de lay-out van paginanummers te bepalen. Zo kunt u de tabstops wijzigen:

```java
Document doc = new Document("Table of contents.docx");

for (Paragraph para : (Iterable<Paragraph>) doc.getChildNodes(NodeType.PARAGRAPH, true))
{
    if (para.getParagraphFormat().getStyle().getStyleIdentifier() >= StyleIdentifier.TOC_1 &&
        para.getParagraphFormat().getStyle().getStyleIdentifier() <= StyleIdentifier.TOC_9)
    {
        //Haal het eerste tabblad op dat in deze paragraaf wordt gebruikt, waarmee de paginanummers worden uitgelijnd.
        TabStop tab = para.getParagraphFormat().getTabStops().get(0);
        
        // Verwijder het oude tabblad.
        para.getParagraphFormat().getTabStops().removeByPosition(tab.getPosition());
        
        // Voeg een nieuw tabblad in op een gewijzigde positie (bijvoorbeeld 50 eenheden naar links).
        para.getParagraphFormat().getTabStops().add(tab.getPosition() - 50.0, tab.getAlignment(), tab.getLeader());
    }
}

doc.save("output.docx");
```

Nu hebt u een aangepaste inhoudsopgave in uw document met aangepaste tabstops voor de uitlijning van de paginanummers.


## Conclusie

In deze zelfstudie hebben we onderzocht hoe u een inhoudsopgave (TOC) kunt genereren met Aspose.Words voor Java, een krachtige bibliotheek voor het werken met Word-documenten. Een goed gestructureerde inhoudsopgave is essentieel voor het organiseren van en navigeren door lange documenten, en Aspose.Words biedt de tools om moeiteloos inhoudsopgaven te maken en aan te passen.

## Veelgestelde vragen

### Hoe wijzig ik de opmaak van inhoudsopgave-items?

 U kunt de stijlen die aan TOC-niveaus zijn gekoppeld wijzigen met behulp van`doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_X)`, waarbij X het TOC-niveau is.

### Hoe kan ik meer niveaus aan mijn inhoudsopgave toevoegen?

Om meer niveaus in uw inhoudsopgave op te nemen, kunt u het inhoudsopgaveveld wijzigen en het gewenste aantal niveaus opgeven.

### Kan ik de tabstopposities voor specifieke inhoudsopgave-items wijzigen?

Ja, zoals weergegeven in het bovenstaande codevoorbeeld, kunt u de tabstopposities voor specifieke inhoudsopgave-items wijzigen door de alinea's te doorlopen en de tabstops dienovereenkomstig aan te passen.