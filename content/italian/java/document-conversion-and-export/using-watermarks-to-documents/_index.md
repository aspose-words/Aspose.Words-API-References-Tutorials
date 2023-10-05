---
title: Utilizzo di filigrane sui documenti in Aspose.Words per Java
linktitle: Utilizzo di filigrane sui documenti
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come aggiungere filigrane ai documenti in Aspose.Words per Java. Personalizza filigrane di testo e immagini per documenti dall'aspetto professionale.
type: docs
weight: 15
url: /it/java/document-conversion-and-export/using-watermarks-to-documents/
---

## Introduzione all'aggiunta di filigrane ai documenti in Aspose.Words per Java

In questo tutorial esploreremo come aggiungere filigrane ai documenti utilizzando l'API Aspose.Words per Java. Le filigrane rappresentano un modo utile per etichettare i documenti con testo o grafica per indicarne lo stato, la riservatezza o altre informazioni rilevanti. In questa guida tratteremo sia le filigrane di testo che quelle di immagini.

## Configurazione di Aspose.Words per Java

Prima di iniziare ad aggiungere filigrane ai documenti, dobbiamo configurare Aspose.Words per Java. Segui questi passaggi per iniziare:

1.  Scarica Aspose.Words per Java da[Qui](https://releases.aspose.com/words/java/).
2. Aggiungi la libreria Aspose.Words per Java al tuo progetto Java.
3. Importa le classi necessarie nel tuo codice Java.

Ora che abbiamo configurato la libreria, procediamo con l'aggiunta di filigrane.

## Aggiunta di filigrane di testo

Le filigrane di testo sono una scelta comune quando desideri aggiungere informazioni testuali ai tuoi documenti. Ecco come puoi aggiungere una filigrana di testo utilizzando Aspose.Words per Java:

```java
//Crea un'istanza del documento
Document doc = new Document("Document.docx");

// Definire le opzioni TextWatermark
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

// Imposta il testo e le opzioni della filigrana
doc.getWatermark().setText("Test", options);

// Salva il documento con la filigrana
doc.save("DocumentWithWatermark.docx");
```

## Aggiunta di filigrane alle immagini

Oltre alle filigrane di testo, puoi anche aggiungere filigrane di immagini ai tuoi documenti. Ecco come aggiungere una filigrana all'immagine:

```java
//Crea un'istanza del documento
Document doc = new Document("Document.docx");

// Carica l'immagine per la filigrana
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

// Imposta la dimensione e la posizione della filigrana
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

// Aggiungi la filigrana al documento
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Salva il documento con la filigrana
doc.save("DocumentWithImageWatermark.docx");
```

## Personalizzazione delle filigrane

Puoi personalizzare le filigrane modificandone l'aspetto e la posizione. Per le filigrane di testo, puoi modificare il carattere, la dimensione, il colore e il layout. Per le filigrane delle immagini, puoi modificarne le dimensioni e la posizione come dimostrato negli esempi precedenti.

## Rimozione di filigrane

Per rimuovere filigrane da un documento, puoi utilizzare il seguente codice:

```java
//Crea un'istanza del documento
Document doc = new Document("DocumentWithWatermark.docx");

// Rimuovi la filigrana
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

// Salva il documento senza filigrana
doc.save("DocumentWithoutWatermark.docx");
```


## Conclusione

In questo tutorial, abbiamo imparato come aggiungere filigrane ai documenti utilizzando Aspose.Words per Java. Se è necessario aggiungere filigrane di testo o immagini, Aspose.Words fornisce gli strumenti per personalizzarli e gestirli in modo efficiente. Puoi anche rimuovere le filigrane quando non sono più necessarie, garantendo che i tuoi documenti siano puliti e professionali.

## Domande frequenti

### Come posso cambiare il carattere di una filigrana di testo?

 Per cambiare il carattere di una filigrana di testo, modificare il file`setFontFamily` proprietà nel`TextWatermarkOptions`. Per esempio:

```java
options.setFontFamily("Times New Roman");
```

### Posso aggiungere più filigrane a un singolo documento?

 Sì, puoi aggiungere più filigrane a un documento creandone più`Shape` oggetti con impostazioni diverse e aggiungerli al documento.

### È possibile ruotare una filigrana?

 Sì, puoi ruotare una filigrana impostando il file`setRotation` proprietà nel`Shape` oggetto. I valori positivi ruotano la filigrana in senso orario, mentre i valori negativi la ruotano in senso antiorario.

### Come posso rendere semitrasparente una filigrana?

 Per rendere semitrasparente una filigrana, impostare il file`setSemitransparent`proprietà a`true` nel`TextWatermarkOptions`.

### Posso aggiungere filigrane a sezioni specifiche di un documento?

Sì, puoi aggiungere filigrane a sezioni specifiche di un documento scorrendo le sezioni e aggiungendo la filigrana alle sezioni desiderate.