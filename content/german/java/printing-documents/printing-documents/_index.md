---
title: Drucken von Dokumenten in Aspose.Words für Java
linktitle: Drucken von Dokumenten
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Dokumente mit Aspose.Words für Java drucken. Schritt-für-Schritt-Anleitung für nahtloses Drucken in Ihren Java-Anwendungen.
type: docs
weight: 10
url: /de/java/printing-documents/printing-documents/
---

Wenn Sie Dokumente mit Aspose.Words für Java drucken möchten, sind Sie hier richtig. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch den Prozess des Druckens von Dokumenten mit Aspose.Words für Java unter Verwendung des bereitgestellten Quellcodes.

## Einführung

Das Drucken von Dokumenten ist in vielen Anwendungen eine häufige Aufgabe. Aspose.Words für Java bietet eine leistungsstarke API für die Arbeit mit Word-Dokumenten, einschließlich der Möglichkeit, diese zu drucken. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess des Druckens eines Word-Dokuments.

## Einrichten Ihrer Umgebung

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Java Development Kit (JDK) installiert
- Aspose.Words für Java-Bibliothek heruntergeladen und Ihrem Projekt hinzugefügt

## Laden des Dokuments

 Um zu beginnen, müssen Sie das Word-Dokument laden, das Sie drucken möchten. Ersetzen`"Your Document Directory"` mit dem Pfad zu Ihrem Dokument und`"Your Output Directory"` mit dem gewünschten Ausgabeverzeichnis.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Erstellen eines Druckauftrags

Als Nächstes erstellen wir einen Druckauftrag, um unser geladenes Dokument zu drucken. Der folgende Codeausschnitt initialisiert einen Druckauftrag und legt die gewünschten Druckereinstellungen fest.

```java
// Erstellen Sie einen Druckauftrag, um unser Dokument auszudrucken.
PrinterJob pj = PrinterJob.getPrinterJob();
//Initialisieren Sie einen Attributsatz mit der Anzahl der Seiten im Dokument.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Übergeben Sie die Druckereinstellungen zusammen mit den anderen Parametern an das Druckdokument.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## Drucken des Dokuments

Nachdem wir nun unseren Druckauftrag eingerichtet haben, ist es an der Zeit, das Dokument zu drucken. Der folgende Codeausschnitt verknüpft das Dokument mit dem Druckauftrag und leitet den Druckvorgang ein.

```java
// Übergeben Sie das zu druckende Dokument mit dem Druckauftrag.
pj.setPrintable(awPrintDoc);
pj.print();
```
## Vollständiger Quellcode
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// Erstellen Sie einen Druckauftrag, um unser Dokument auszudrucken.
PrinterJob pj = PrinterJob.getPrinterJob();
//Initialisieren Sie einen Attributsatz mit der Anzahl der Seiten im Dokument.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Übergeben Sie die Druckereinstellungen zusammen mit den anderen Parametern an das Druckdokument.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// Übergeben Sie das zu druckende Dokument mit dem Druckauftrag.
pj.setPrintable(awPrintDoc);
pj.print();
```
Quellcode von MultipagePrintDocument
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <Zusammenfassung>
    /// Der Konstruktor der benutzerdefinierten PrintDocument-Klasse.
    // / </summary>
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
        // Die Seitenanfangs- und -endindizes, wie im Attributsatz definiert.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // Berechnen Sie den Seitenindex, der als nächstes gerendert werden soll.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // Wenn der Seitenindex größer ist als der gesamte Seitenbereich, gibt es nichts
        // mehr zu rendern.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // Berechnen Sie die Größe jedes Miniaturbild-Platzhalters in Punkten.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // Berechnen Sie die Nummer der ersten Seite, die auf diesem Blatt Papier gedruckt werden soll.
        int startPage = pagesOnCurrentSheet + fromPage;
        // Wählen Sie die Nummer der letzten Seite aus, die auf diesem Blatt Papier gedruckt werden soll.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //Durchlaufen Sie die ausgewählten Seiten von der gespeicherten aktuellen Seite bis zur berechneten Seite
        // letzte Seite.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // Berechnen Sie die Spalten- und Zeilenindizes.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // Definieren Sie die Position der Miniaturansicht in Weltkoordinaten (in diesem Fall Punkte).
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // Berechnen Sie die linke und obere Startposition.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // Rendern Sie die Dokumentseite mithilfe berechneter Koordinaten im Graphics-Objekt
                // und Miniaturbild-Platzhaltergröße.
                // Der nützliche Rückgabewert ist der Maßstab, in dem die Seite gerendert wurde.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // Zeichnen Sie die Seitenränder (das Seitenminiaturbild könnte kleiner als das Miniaturbild sein).
                // Platzhaltergröße).
                if (mPrintPageBorders) {
                    // Ermitteln Sie die tatsächliche 100 %-Größe der Seite in Punkten.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // Zeichnen Sie den Rahmen um die skalierte Seite mit dem bekannten Skalierungsfaktor.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // Zeichnen Sie den Rahmen um den Miniaturbild-Platzhalter.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // Wenn beim Rendern Fehler auftreten, unternehmen Sie nichts.
                // Dadurch wird eine leere Seite gezeichnet, wenn beim Rendern Fehler auftreten.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // Definieren Sie die Anzahl der Spalten und Zeilen auf dem Blatt für die
        //Landschaftsorientiertes Papier.
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
        // Tauschen Sie Breite und Höhe aus, wenn das Papier im Hochformat vorliegt.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## Abschluss

Glückwunsch! Sie haben erfolgreich ein Word-Dokument mit Aspose.Words für Java gedruckt. Diese Schritt-für-Schritt-Anleitung soll Ihnen dabei helfen, den Dokumentendruck nahtlos in Ihre Java-Anwendungen zu integrieren.

## FAQs

### F1: Kann ich mit Aspose.Words für Java bestimmte Seiten eines Dokuments drucken?

 Ja, Sie können den Seitenbereich beim Drucken eines Dokuments angeben. Im Codebeispiel haben wir verwendet`attributes.add(new PageRanges(1, doc.getPageCount()))` um alle Seiten zu drucken. Sie können den Seitenbereich nach Bedarf anpassen.

### F2: Ist Aspose.Words für Java für den Stapeldruck geeignet?

Absolut! Aspose.Words für Java eignet sich gut für Stapeldruckaufgaben. Sie können eine Liste von Dokumenten durchlaufen und sie mit ähnlichem Code einzeln ausdrucken.

### F3: Wie kann ich mit Druckfehlern oder Ausnahmen umgehen?

Sie sollten alle potenziellen Ausnahmen behandeln, die während des Druckvorgangs auftreten können. Informationen zur Behandlung von Ausnahmen finden Sie in der Dokumentation zu Aspose.Words für Java.

### F4: Kann ich die Druckeinstellungen weiter anpassen?

Ja, Sie können die Druckeinstellungen an Ihre spezifischen Anforderungen anpassen. Erkunden Sie die Aspose.Words for Java-Dokumentation, um mehr über die verfügbaren Druckoptionen zu erfahren.

### F5: Wo erhalte ich weitere Hilfe und Unterstützung für Aspose.Words für Java?

 Für zusätzliche Unterstützung und Unterstützung können Sie die besuchen[Aspose.Words für Java-Forum](https://forum.aspose.com/).

---

Nachdem Sie nun erfolgreich gelernt haben, wie Sie Dokumente mit Aspose.Words für Java drucken, können Sie mit der Implementierung dieser Funktionalität in Ihren Java-Anwendungen beginnen. Viel Spaß beim Codieren!