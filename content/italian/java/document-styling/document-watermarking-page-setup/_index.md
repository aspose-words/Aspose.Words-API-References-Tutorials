---
title: Filigrana del documento e impostazione della pagina
linktitle: Filigrana del documento e impostazione della pagina
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come applicare filigrane e impostare configurazioni di pagina con Aspose.Words per Java. Una guida completa con il codice sorgente.
type: docs
weight: 13
url: /it/java/document-styling/document-watermarking-page-setup/
---
## Introduzione

Nel regno della manipolazione dei documenti, Aspose.Words per Java si pone come un potente strumento, consentendo agli sviluppatori di esercitare il controllo su ogni aspetto dell'elaborazione dei documenti. In questa guida completa, approfondiremo le complessità della filigrana dei documenti e dell'impostazione della pagina utilizzando Aspose.Words per Java. Che tu sia uno sviluppatore esperto o che tu stia semplicemente entrando nel mondo dell'elaborazione dei documenti Java, questa guida passo passo ti fornirà le conoscenze e il codice sorgente di cui hai bisogno.

## Filigrana del documento

### Aggiunta di filigrane

L'aggiunta di filigrane ai documenti può essere fondamentale per il branding o la protezione dei tuoi contenuti. Aspose.Words per Java rende questa attività semplice. Ecco come:

```java
// Caricare il documento
Document doc = new Document("document.docx");

// Crea una filigrana
Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.getTextPath().setText("Confidential");
watermark.setWidth(300);
watermark.setHeight(100);

// Posiziona la filigrana
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.setWrapType(WrapType.NONE);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);

// Inserisci la filigrana
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Salva il documento
doc.save("document_with_watermark.docx");
```

### Personalizzazione delle filigrane

Puoi personalizzare ulteriormente le filigrane regolando carattere, dimensione, colore e rotazione. Questa flessibilità garantisce che la filigrana corrisponda perfettamente allo stile del documento.

## Impostazione pagina

### Dimensioni e orientamento della pagina

L'impostazione della pagina è fondamentale nella formattazione del documento. Aspose.Words per Java offre il controllo completo sulle dimensioni e sull'orientamento della pagina:

```java
// Caricare il documento
Document doc = new Document("document.docx");

// Imposta la dimensione della pagina su A4
doc.getFirstSection().getPageSetup().setPageWidth(595.0);
doc.getFirstSection().getPageSetup().setPageHeight(842.0);

// Cambia l'orientamento della pagina in orizzontale
doc.getFirstSection().getPageSetup().setOrientation(Orientation.LANDSCAPE);

// Salva il documento modificato
doc.save("formatted_document.docx");
```

### Margini e numerazione delle pagine

Il controllo preciso sui margini e sulla numerazione delle pagine è essenziale per i documenti professionali. Ottieni questo risultato con Aspose.Words per Java:

```java
// Caricare il documento
Document doc = new Document("document.docx");

// Imposta i margini
doc.getFirstSection().getPageSetup().setLeftMargin(72.0);
doc.getFirstSection().getPageSetup().setRightMargin(72.0);
doc.getFirstSection().getPageSetup().setTopMargin(72.0);
doc.getFirstSection().getPageSetup().setBottomMargin(72.0);

// Abilita la numerazione delle pagine
doc.getFirstSection().getPageSetup().setDifferentFirstPageHeaderFooter(true);
HeaderFooter firstPageHeader = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_FIRST);
firstPageHeader.appendParagraph("First Page Header");

// Salva il documento formattato
doc.save("formatted_document.docx");
```

## Domande frequenti

### Come posso rimuovere una filigrana da un documento?

Per rimuovere una filigrana da un documento, puoi scorrere le forme del documento e rimuovere quelle che rappresentano le filigrane. Ecco uno snippet:

```java
Document doc = new Document("document_with_watermark.docx");

for (Shape shape : doc.getChildNodes(NodeType.SHAPE, true).<Shape>toArray()) {
    if (shape.getText().contains("Confidential")) {
        shape.remove();
    }
}

doc.save("document_without_watermark.docx");
```

### Posso aggiungere più filigrane a un singolo documento?

Sì, puoi aggiungere più filigrane a un documento creando oggetti Forma aggiuntivi e posizionandoli secondo necessità.

### Come posso modificare la dimensione della pagina in Legale con orientamento orizzontale?

Per impostare la dimensione della pagina su legale con orientamento orizzontale, modificare la larghezza e l'altezza della pagina come segue:

```java
doc.getFirstSection().getPageSetup().setPageWidth(842.0);
doc.getFirstSection().getPageSetup().setPageHeight(595.0);
```

### Qual è il carattere predefinito per le filigrane?

Il carattere predefinito per le filigrane è Calibri con una dimensione del carattere pari a 36.

### Come posso aggiungere i numeri di pagina a partire da una pagina specifica?

Puoi ottenere ciò impostando il numero di pagina iniziale nel documento come segue:

```java
doc.getFirstSection().getPageSetup().setPageStartingNumber(5);
```

### Come posso centrare il testo nell'intestazione o nel piè di pagina?

È possibile centrare il testo nell'intestazione o nel piè di pagina utilizzando il metodo setAlignment sull'oggetto Paragraph all'interno dell'intestazione o del piè di pagina.

## Conclusione

In questa guida estesa, abbiamo esplorato l'arte della filigrana dei documenti e dell'impostazione della pagina utilizzando Aspose.Words per Java. Armato degli snippet e degli approfondimenti del codice sorgente forniti, ora possiedi gli strumenti per manipolare e formattare i tuoi documenti con finezza. Aspose.Words per Java ti consente di creare documenti professionali e brandizzati su misura per le tue esatte specifiche.

Padroneggiare la manipolazione dei documenti è un'abilità preziosa per gli sviluppatori e Aspose.Words per Java è il tuo compagno fidato in questo viaggio. Inizia a creare documenti straordinari oggi!