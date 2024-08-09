---
title: Salvataggio di documenti come PDF in Aspose.Words per Java
linktitle: Salvataggio di documenti come PDF
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come salvare documenti Word come PDF utilizzando Aspose.Words per Java. Personalizza caratteri, proprietà e qualità dell'immagine. Una guida completa per la conversione di PDF.
type: docs
weight: 22
url: /it/java/document-loading-and-saving/saving-documents-as-pdf/
---

## Introduzione al salvataggio di documenti come PDF in Aspose.Words per Java

In questa guida passo passo, esploreremo come salvare documenti come PDF utilizzando Aspose.Words per Java. Tratteremo vari aspetti della conversione PDF e forniremo esempi di codice per semplificare il processo.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Java Development Kit (JDK) installato sul tuo sistema.
-  Aspose.Words per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/words/java/).

## Conversione di un documento in PDF

Per convertire un documento Word in PDF, puoi utilizzare il seguente snippet di codice:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Sostituire`"input.docx"` con il percorso del documento Word e`"output.pdf"` con il percorso del file PDF di output desiderato.

## Controllo delle opzioni di salvataggio del PDF

 Puoi controllare varie opzioni di salvataggio PDF utilizzando`PdfSaveOptions` classe. Ad esempio, puoi impostare il titolo visualizzato per il documento PDF come segue:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## Incorporamento di caratteri nel PDF

Per incorporare i caratteri nel PDF generato, utilizzare il seguente codice:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## Personalizzazione delle proprietà del documento

È possibile personalizzare le proprietà del documento nel PDF generato. Per esempio:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## Esportazione della struttura del documento

 Per esportare la struttura del documento, impostare il file`exportDocumentStructure` opzione a`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## Compressione delle immagini

Puoi controllare la compressione delle immagini utilizzando il seguente codice:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## Aggiornamento dell'ultima proprietà stampata

Per aggiornare la proprietà "Ultima stampata" nel PDF, utilizzare:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## Rendering di effetti 3D DML

Per il rendering avanzato degli effetti 3D DML, imposta la modalità di rendering:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## Interpolazione di immagini

È possibile abilitare l'interpolazione delle immagini per migliorare la qualità dell'immagine:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## Conclusione

Aspose.Words per Java offre funzionalità complete per convertire documenti Word in formato PDF con flessibilità e opzioni di personalizzazione. Puoi controllare vari aspetti dell'output PDF, inclusi caratteri, proprietà del documento, compressione delle immagini e altro.

## Domande frequenti

### Come posso convertire un documento Word in PDF utilizzando Aspose.Words per Java?

Per convertire un documento Word in PDF, utilizzare il seguente codice:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Sostituire`"input.docx"` con il percorso del documento Word e`"output.pdf"` con il percorso del file PDF di output desiderato.

### Posso incorporare caratteri nel PDF generato da Aspose.Words per Java?

 Sì, puoi incorporare caratteri nel PDF impostando il file`setEmbedFullFonts` opzione a`true` In`PdfSaveOptions`. Ecco un esempio:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### Come posso personalizzare le proprietà del documento nel PDF generato?

 È possibile personalizzare le proprietà del documento nel PDF utilizzando il file`setCustomPropertiesExport` opzione dentro`PdfSaveOptions`. Per esempio:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### Qual è lo scopo della compressione delle immagini in Aspose.Words per Java?

 La compressione delle immagini consente di controllare la qualità e la dimensione delle immagini nel PDF generato. È possibile impostare la modalità di compressione dell'immagine utilizzando`setImageCompression` In`PdfSaveOptions`.

### Come posso aggiornare la proprietà "Ultima stampata" nel PDF?

 È possibile aggiornare la proprietà "Ultima stampata" nel PDF impostando`setUpdateLastPrintedProperty` A`true` In`PdfSaveOptions`. Ciò rifletterà l'ultima data stampata nei metadati del PDF.

### Come posso migliorare la qualità dell'immagine durante la conversione in PDF?

 Per migliorare la qualità dell'immagine, abilitare l'interpolazione dell'immagine impostando`setInterpolateImages` A`true` In`PdfSaveOptions`. Ciò si tradurrà in immagini più fluide e di qualità superiore nel PDF.