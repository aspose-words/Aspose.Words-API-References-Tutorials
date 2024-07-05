---
title: Opzioni avanzate di salvataggio dei documenti HTML con Aspose.Words Java
linktitle: Salvataggio di documenti HTML con
second_title: API di elaborazione dei documenti Java Aspose.Words
description: In questo tutorial, abbiamo trattato varie opzioni avanzate di salvataggio di documenti HTML con Aspose.Words per Java. Queste opzioni ti consentono di creare HTML di alta qualità
type: docs
weight: 16
url: /it/java/document-loading-and-saving/advance-html-documents-saving-options/
---

In questo tutorial esploreremo le opzioni avanzate di salvataggio dei documenti HTML fornite da Aspose.Words per Java. Aspose.Words è una potente API Java per lavorare con documenti Word e offre un'ampia gamma di funzionalità per la manipolazione e la conversione dei documenti.

## 1. Introduzione
Aspose.Words per Java ti consente di lavorare con documenti Word a livello di codice. In questo tutorial ci concentreremo sulle opzioni avanzate di salvataggio dei documenti HTML, che ti consentono di controllare il modo in cui i documenti Word vengono convertiti in HTML.

## 2. Esportazione delle informazioni di andata e ritorno
 IL`exportRoundtripInformation` Il metodo consente di esportare documenti Word in HTML preservando le informazioni di andata e ritorno. Queste informazioni possono essere utili quando desideri riconvertire l'HTML nel formato Word senza perdere i dettagli specifici del documento.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Esporta i caratteri come Base64
 Con il`exportFontsAsBase64` metodo, è possibile esportare i caratteri utilizzati nel documento come dati con codifica Base64 nell'HTML. Ciò garantisce che la rappresentazione HTML mantenga gli stessi stili di carattere del documento Word originale.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Esportare risorse
 IL`exportResources` Il metodo consente di specificare il tipo di foglio di stile CSS ed esportare le risorse dei caratteri. Puoi anche impostare una cartella di risorse e un alias per le risorse nell'HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://esempio.com/risorse");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Converti metafile in EMF o WMF
 IL`convertMetafilesToEmfOrWmf`Il metodo consente di convertire i metafile nel documento nel formato EMF o WMF, garantendo compatibilità e rendering uniforme in HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Snippet di codice non mostrato per brevità.
}
```

## 6. Converti metafile in SVG
 Usa il`convertMetafilesToSvg` metodo per convertire i metafile nel formato SVG. Questo formato è ideale per visualizzare grafica vettoriale in documenti HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Snippet di codice non mostrato per brevità.
}
```

## 7. Aggiungi il prefisso del nome della classe CSS
 Con il`addCssClassNamePrefix` metodo, puoi aggiungere un prefisso ai nomi delle classi CSS nell'HTML esportato. Ciò aiuta a prevenire conflitti con gli stili esistenti.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. Esporta URL CID per risorse MHTML
 IL`exportCidUrlsForMhtmlResources` viene utilizzato quando si salvano documenti in formato MHTML. Consente di esportare URL di Content-ID per le risorse.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Snippet di codice non mostrato per brevità.
}
```

## 9. Risolvi i nomi dei caratteri
 IL`resolveFontNames` Il metodo aiuta a risolvere i nomi dei caratteri durante il salvataggio di documenti in formato HTML, garantendo un rendering coerente su piattaforme diverse.

```java
@Test
public void resolveFontNames() throws Exception {
    // Snippet di codice non mostrato per brevità.
}
```

## 10. Esporta il campo del modulo di input testo come testo
 IL`exportTextInputFormFieldAsText` Il metodo esporta i campi del modulo come testo semplice nell'HTML, rendendoli facilmente leggibili e modificabili.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Snippet di codice non mostrato per brevità.
}
```

## 11. Conclusione
In questo tutorial, abbiamo esplorato le opzioni avanzate di salvataggio dei documenti HTML fornite da Aspose.Words per Java. Queste opzioni ti offrono un controllo capillare sul processo di conversione, permettendoti di creare documenti HTML che assomigliano molto ai documenti Word originali.

## 12. Domande frequenti
Ecco alcune domande frequenti sull'utilizzo di Aspose.Words per Java e le opzioni di salvataggio dei documenti HTML:

### Q1: Come posso riconvertire l'HTML in formato Word utilizzando Aspose.Words per Java?
 Per riconvertire l'HTML in formato Word, puoi utilizzare le API Aspose.Words`load` metodo per caricare il documento HTML e poi salvarlo in formato Word.

### Q2: Posso personalizzare gli stili CSS durante l'esportazione in HTML?
 Sì, puoi personalizzare gli stili CSS modificando i fogli di stile utilizzati nell'HTML o utilizzando il file`addCssClassNamePrefix` metodo per aggiungere un prefisso ai nomi delle classi CSS.

### Q3: Esiste un modo per ottimizzare l'output HTML per la visualizzazione sul Web?
Sì, puoi ottimizzare l'output HTML per la visualizzazione sul Web configurando opzioni come l'esportazione di caratteri come Base64 e la conversione di metafile in SVG.

### Q4: Esistono limitazioni durante la conversione di documenti Word complessi in HTML?
Sebbene Aspose.Words per Java offra potenti funzionalità di conversione, documenti Word complessi con layout intricati potrebbero richiedere un'ulteriore post-elaborazione per ottenere l'output HTML desiderato.
