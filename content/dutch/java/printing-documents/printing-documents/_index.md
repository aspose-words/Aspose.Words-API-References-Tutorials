---
title: Documenten afdrukken in Aspose.Words voor Java
linktitle: Documenten afdrukken
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u documenten kunt afdrukken met Aspose.Words voor Java. Stapsgewijze handleiding voor naadloos printen in uw Java-toepassingen.
type: docs
weight: 10
url: /nl/java/printing-documents/printing-documents/
---

Als u documenten wilt afdrukken met Aspose.Words voor Java, bent u hier aan het juiste adres. In deze stapsgewijze handleiding leiden we u door het proces van het afdrukken van documenten met Aspose.Words voor Java met behulp van de meegeleverde broncode.

## Invoering

Het afdrukken van documenten is in veel toepassingen een veel voorkomende taak. Aspose.Words voor Java biedt een krachtige API om met Word-documenten te werken, inclusief de mogelijkheid om deze af te drukken. In deze tutorial begeleiden we u stap voor stap bij het afdrukken van een Word-document.

## Uw omgeving instellen

Voordat we in de code duiken, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:

- Java Development Kit (JDK) geïnstalleerd
- Aspose.Words voor Java-bibliotheek gedownload en toegevoegd aan uw project

## Het document laden

 Om aan de slag te gaan, moet u het Word-document laden dat u wilt afdrukken. Vervangen`"Your Document Directory"` met het pad naar uw document en`"Your Output Directory"` met de gewenste uitvoermap.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Een afdruktaak maken

Vervolgens maken we een afdruktaak om ons geladen document af te drukken. Het onderstaande codefragment initialiseert een afdruktaak en stelt de gewenste printerinstellingen in.

```java
// Maak een afdruktaak aan om ons document mee af te drukken.
PrinterJob pj = PrinterJob.getPrinterJob();
//Initialiseer een attribuutset met het aantal pagina's in het document.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Geef de printerinstellingen samen met de andere parameters door aan het afdrukdocument.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## Het document afdrukken

Nu we onze afdruktaak hebben ingesteld, is het tijd om het document af te drukken. Het volgende codefragment koppelt het document aan de afdruktaak en start het afdrukproces.

```java
// Geef het af te drukken document door via de afdruktaak.
pj.setPrintable(awPrintDoc);
pj.print();
```
## Volledige broncode
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// Maak een afdruktaak aan om ons document mee af te drukken.
PrinterJob pj = PrinterJob.getPrinterJob();
//Initialiseer een attribuutset met het aantal pagina's in het document.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Geef de printerinstellingen samen met de andere parameters door aan het afdrukdocument.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// Geef het af te drukken document door via de afdruktaak.
pj.setPrintable(awPrintDoc);
pj.print();
```
Broncode van MultipagePrintDocument
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <samenvatting>
    /// De constructor van de aangepaste PrintDocument-klasse.
    // /</samenvatting>
    public MultipagePrintDocument(Document document, int pagesPerSheet, boolean printPageBorders,
                                  AttributeSet attributes) {
        if (document == null)
            throw new IllegalArgumentException("document");
        mDocument = document;
        mPagesPerSheet = pagesPerSheet;
        mPrintPageBorders = printPageBorders;
        mAttributeSet = attributes;
    }
    public int print(Graphics g, PageFormat pf, int page) {
        // De start- en eindindexen van de pagina zoals gedefinieerd in de attribuutset.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // Bereken de pagina-index die vervolgens moet worden weergegeven.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // Als de pagina-index groter is dan het totale paginabereik, is er niets
        // meer te renderen.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // Bereken de grootte van elke tijdelijke aanduiding voor de miniatuur in punten.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // Bereken het nummer van de eerste pagina die op dit vel papier moet worden afgedrukt.
        int startPage = pagesOnCurrentSheet + fromPage;
        // Selecteer het nummer van de laatste pagina die op dit vel papier moet worden afgedrukt.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //Loop door de geselecteerde pagina's vanaf de opgeslagen huidige pagina tot berekend
        // laatste pagina.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // Bereken de kolom- en rij-indexen.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // Definieer de miniatuurlocatie in wereldcoördinaten (in dit geval punten).
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // Bereken de linker en bovenste startpositie.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // Render de documentpagina naar het Graphics-object met behulp van berekende coördinaten
                // en de grootte van de tijdelijke aanduiding voor de miniatuur.
                // De bruikbare retourwaarde is de schaal waarop de pagina is weergegeven.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // Teken de paginaranden (de paginaminiatuur kan kleiner zijn dan de miniatuur
                // grootte van tijdelijke aanduiding).
                if (mPrintPageBorders) {
                    // Krijg de echte 100% grootte van de pagina in punten.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // Teken de rand rond de geschaalde pagina met behulp van de bekende schaalfactor.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // Teken de rand rond de tijdelijke aanduiding voor de miniatuur.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // Als er fouten optreden tijdens het renderen, doe dan niets.
                // Hierdoor wordt een lege pagina getekend als er fouten optreden tijdens het renderen.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // Definieer het aantal kolommen en rijen op het blad voor de
        //Liggend papier.
        switch (pagesPerSheet) {
            case 16:
                size = new Dimension(4, 4);
                break;
            case 9:
                size = new Dimension(3, 3);
                break;
            case 8:
                size = new Dimension(4, 2);
                break;
            case 6:
                size = new Dimension(3, 2);
                break;
            case 4:
                size = new Dimension(2, 2);
                break;
            case 2:
                size = new Dimension(2, 1);
                break;
            default:
                size = new Dimension(1, 1);
                break;
        }
        // Wissel de breedte en hoogte om als het papier in de staande richting staat.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## Conclusie

Gefeliciteerd! U hebt met succes een Word-document afgedrukt met Aspose.Words voor Java. Met deze stapsgewijze handleiding kunt u het afdrukken van documenten naadloos in uw Java-toepassingen integreren.

## Veelgestelde vragen

### V1: Kan ik specifieke pagina's van een document afdrukken met Aspose.Words voor Java?

 Ja, u kunt het paginabereik opgeven wanneer u een document afdrukt. In het codevoorbeeld gebruikten we`attributes.add(new PageRanges(1, doc.getPageCount()))` om alle pagina's af te drukken. U kunt het paginabereik indien nodig aanpassen.

### V2: Is Aspose.Words voor Java geschikt voor batchafdrukken?

Absoluut! Aspose.Words voor Java is zeer geschikt voor batchafdruktaken. U kunt door een lijst met documenten bladeren en ze één voor één afdrukken met behulp van vergelijkbare code.

### Vraag 3: Hoe kan ik omgaan met drukfouten of uitzonderingen?

dient eventuele uitzonderingen die zich tijdens het afdrukproces kunnen voordoen, af te handelen. Raadpleeg de Aspose.Words voor Java-documentatie voor informatie over het omgaan met uitzonderingen.

### Vraag 4: Kan ik de afdrukinstellingen verder aanpassen?

Ja, u kunt de afdrukinstellingen aanpassen aan uw specifieke wensen. Verken de Aspose.Words voor Java-documentatie voor meer informatie over beschikbare afdrukopties.

### V5: Waar kan ik meer hulp en ondersteuning krijgen voor Aspose.Words voor Java?

 Voor extra ondersteuning en assistentie kunt u terecht op de[Aspose.Words voor Java-forum](https://forum.aspose.com/).

---

Nu u met succes heeft geleerd hoe u documenten kunt afdrukken met Aspose.Words voor Java, kunt u beginnen met het implementeren van deze functionaliteit in uw Java-toepassingen. Veel codeerplezier!