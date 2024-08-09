---
title: Stampa di documenti in Aspose.Words per Java
linktitle: Stampa di documenti
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come stampare documenti utilizzando Aspose.Words per Java. Guida passo passo per stampare senza problemi nelle tue applicazioni Java.
type: docs
weight: 10
url: /it/java/printing-documents/printing-documents/
---

Se stai cercando di stampare documenti utilizzando Aspose.Words per Java, sei nel posto giusto. In questa guida passo passo ti guideremo attraverso il processo di stampa di documenti con Aspose.Words per Java utilizzando il codice sorgente fornito.

## Introduzione

La stampa di documenti è un'attività comune in molte applicazioni. Aspose.Words per Java fornisce una potente API per lavorare con documenti Word, inclusa la possibilità di stamparli. In questo tutorial ti guideremo passo dopo passo attraverso il processo di stampa di un documento Word.

## Configurazione dell'ambiente

Prima di immergerci nel codice, assicurati di avere i seguenti prerequisiti:

- Kit di sviluppo Java (JDK) installato
- Libreria Aspose.Words per Java scaricata e aggiunta al tuo progetto

## Caricamento del documento

 Per iniziare, dovrai caricare il documento Word che desideri stampare. Sostituire`"Your Document Directory"` con il percorso del documento e`"Your Output Directory"` con la directory di output desiderata.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Creazione di un lavoro di stampa

Successivamente, creeremo un lavoro di stampa per stampare il documento caricato. Lo snippet di codice riportato di seguito inizializza un lavoro di stampa e imposta le impostazioni della stampante desiderate.

```java
// Crea un lavoro di stampa con cui stampare il nostro documento.
PrinterJob pj = PrinterJob.getPrinterJob();
//Inizializza un attributo impostato con il numero di pagine del documento.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Passare le impostazioni della stampante insieme agli altri parametri al documento di stampa.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## Stampa del documento

Ora che abbiamo impostato il nostro lavoro di stampa, è il momento di stampare il documento. Il seguente frammento di codice associa il documento al lavoro di stampa e avvia il processo di stampa.

```java
// Passare il documento da stampare utilizzando il lavoro di stampa.
pj.setPrintable(awPrintDoc);
pj.print();
```
## Codice sorgente completo
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// Crea un lavoro di stampa con cui stampare il nostro documento.
PrinterJob pj = PrinterJob.getPrinterJob();
//Inizializza un attributo impostato con il numero di pagine del documento.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Passare le impostazioni della stampante insieme agli altri parametri al documento di stampa.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// Passare il documento da stampare utilizzando il lavoro di stampa.
pj.setPrintable(awPrintDoc);
pj.print();
```
Codice sorgente di MultipagePrintDocument
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <riepilogo>
    /// Il costruttore della classe PrintDocument personalizzata.
    // /</summary>
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
        // Gli indici di inizio e fine della pagina come definiti nel set di attributi.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // Calcola l'indice della pagina che deve essere visualizzato successivamente.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // Se l'indice della pagina è superiore all'intervallo di pagine totale, non c'è nulla
        // altro da rendere.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // Calcola la dimensione di ciascun segnaposto miniatura in punti.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // Calcola il numero della prima pagina da stampare su questo foglio di carta.
        int startPage = pagesOnCurrentSheet + fromPage;
        // Selezionare il numero dell'ultima pagina da stampare su questo foglio di carta.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //Passa attraverso le pagine selezionate dalla pagina corrente memorizzata a quella calcolata
        // ultima pagina.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // Calcolare gli indici di colonna e di riga.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // Definire la posizione della miniatura nelle coordinate mondiali (punti in questo caso).
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // Calcolare le posizioni iniziali sinistra e superiore.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // Eseguire il rendering della pagina del documento sull'oggetto Graphics utilizzando le coordinate calcolate
                // e la dimensione del segnaposto della miniatura.
                // Il valore restituito utile è la scala con cui è stato eseguito il rendering della pagina.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // Disegna i bordi della pagina (la miniatura della pagina potrebbe essere più piccola della miniatura
                // dimensione del segnaposto).
                if (mPrintPageBorders) {
                    // Ottieni la dimensione reale del 100% della pagina in punti.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // Disegna il bordo attorno alla pagina ridimensionata utilizzando il fattore di scala noto.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // Disegna il bordo attorno al segnaposto della miniatura.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // Se si verificano errori durante il rendering, non fare nulla.
                // Questo disegnerà una pagina vuota se ci sono errori durante il rendering.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // Definire il numero di colonne e righe sul foglio per
        //Carta orientata al paesaggio.
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
        // Scambia la larghezza e l'altezza se la carta ha l'orientamento verticale.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## Conclusione

Congratulazioni! Hai stampato con successo un documento Word utilizzando Aspose.Words per Java. Questa guida passo passo dovrebbe aiutarti a integrare perfettamente la stampa di documenti nelle tue applicazioni Java.

## Domande frequenti

### Q1: Posso stampare pagine specifiche di un documento utilizzando Aspose.Words per Java?

 Sì, puoi specificare l'intervallo di pagine quando stampi un documento. Nell'esempio di codice, abbiamo usato`attributes.add(new PageRanges(1, doc.getPageCount()))` per stampare tutte le pagine. È possibile regolare l'intervallo di pagine secondo necessità.

### Q2: Aspose.Words per Java è adatto per la stampa batch?

Assolutamente! Aspose.Words per Java è adatto per attività di stampa batch. È possibile scorrere un elenco di documenti e stamparli uno per uno utilizzando un codice simile.

### Q3: Come posso gestire gli errori o le eccezioni di stampa?

È necessario gestire eventuali eccezioni che potrebbero verificarsi durante il processo di stampa. Controlla la documentazione di Aspose.Words per Java per informazioni sulla gestione delle eccezioni.

### Q4: Posso personalizzare ulteriormente le impostazioni di stampa?

Sì, puoi personalizzare le impostazioni di stampa per soddisfare le tue esigenze specifiche. Esplora la documentazione di Aspose.Words per Java per ulteriori informazioni sulle opzioni di stampa disponibili.

### Q5: Dove posso ottenere ulteriore aiuto e supporto per Aspose.Words per Java?

 Per ulteriore supporto e assistenza, è possibile visitare il[Forum Aspose.Words per Java](https://forum.aspose.com/).

---

Ora che hai imparato con successo come stampare documenti utilizzando Aspose.Words per Java, puoi iniziare a implementare questa funzionalità nelle tue applicazioni Java. Buona programmazione!