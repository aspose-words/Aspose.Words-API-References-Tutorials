---
title: Opzioni avanzate di salvataggio dei documenti HTML con Aspose.Words Java
linktitle: Salvataggio di documenti HTML con
second_title: API di elaborazione dei documenti Java Aspose.Words
description: In questo tutorial, abbiamo trattato varie opzioni avanzate di salvataggio di documenti HTML con Aspose.Words per Java. Queste opzioni ti consentono di creare documenti HTML di alta qualità
type: docs
weight: 16
url: /it/java/document-loading-and-saving/advance-html-documents-saving-options/
---

In questo tutorial, esploreremo le opzioni avanzate di salvataggio dei documenti HTML fornite da Aspose.Words per Java. Aspose.Words è una potente API Java per lavorare con i documenti Word e offre un'ampia gamma di funzionalità per la manipolazione e la conversione dei documenti.

## 1. Introduzione
Aspose.Words per Java consente di lavorare con i documenti Word a livello di programmazione. In questo tutorial, ci concentreremo sulle opzioni avanzate di salvataggio dei documenti HTML, che consentono di controllare il modo in cui i documenti Word vengono convertiti in HTML.

## 2. Esportazione delle informazioni di andata e ritorno
IL`exportRoundtripInformation` metodo consente di esportare documenti Word in HTML preservando le informazioni di andata e ritorno. Queste informazioni possono essere utili quando si desidera riconvertire HTML in formato Word senza perdere alcun dettaglio specifico del documento.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Esporta i font come Base64
 Con il`exportFontsAsBase64` metodo, puoi esportare i font utilizzati nel documento come dati codificati in Base64 nell'HTML. Ciò assicura che la rappresentazione HTML mantenga gli stessi stili di font del documento Word originale.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Esportazione delle risorse
IL`exportResources` metodo consente di specificare il tipo di foglio di stile CSS ed esportare risorse font. È anche possibile impostare una cartella di risorse e un alias per le risorse nell'HTML.

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

## 5. Convertire i metafile in EMF o WMF
IL`convertMetafilesToEmfOrWmf`Il metodo consente di convertire i metafile presenti nel documento nel formato EMF o WMF, garantendo compatibilità e un rendering fluido in HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Per motivi di brevità il frammento di codice non viene mostrato.
}
```

## 6. Convertire i metafile in SVG
 Utilizzare il`convertMetafilesToSvg` metodo per convertire i metafile in formato SVG. Questo formato è ideale per visualizzare la grafica vettoriale nei documenti HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Per motivi di brevità il frammento di codice non viene mostrato.
}
```

## 7. Aggiungi il prefisso del nome della classe CSS
 Con il`addCssClassNamePrefix` metodo, puoi aggiungere un prefisso ai nomi delle classi CSS nell'HTML esportato. Questo aiuta a prevenire conflitti con gli stili esistenti.

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

## 8. Esportare URL CID per risorse MHTML
IL`exportCidUrlsForMhtmlResources` metodo viene utilizzato quando si salvano documenti in formato MHTML. Consente di esportare URL Content-ID per le risorse.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Per motivi di brevità il frammento di codice non viene mostrato.
}
```

## 9. Risolvi i nomi dei font
IL`resolveFontNames` Il metodo aiuta a risolvere i nomi dei font quando si salvano documenti in formato HTML, garantendo un rendering coerente su diverse piattaforme.

```java
@Test
public void resolveFontNames() throws Exception {
    // Per motivi di brevità il frammento di codice non viene mostrato.
}
```

## 10. Esporta il campo del modulo di immissione testo come testo
IL`exportTextInputFormFieldAsText` Il metodo esporta i campi del modulo come testo normale in HTML, rendendoli facilmente leggibili e modificabili.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Per motivi di brevità il frammento di codice non viene mostrato.
}
```

## 11. Conclusion
In questo tutorial, abbiamo esplorato le opzioni avanzate di salvataggio dei documenti HTML fornite da Aspose.Words per Java. Queste opzioni ti offrono un controllo dettagliato sul processo di conversione, consentendoti di creare documenti HTML che assomigliano molto ai documenti Word originali.

## 12. Domande frequenti
Ecco alcune domande frequenti sull'utilizzo di Aspose.Words per Java e sulle opzioni di salvataggio dei documenti HTML:

### D1: Come posso riconvertire l'HTML nel formato Word utilizzando Aspose.Words per Java?
 Per convertire nuovamente l'HTML nel formato Word, puoi utilizzare le API di Aspose.Words`load` Metodo per caricare il documento HTML e poi salvarlo in formato Word.

### D2: Posso personalizzare gli stili CSS durante l'esportazione in HTML?
 Sì, puoi personalizzare gli stili CSS modificando i fogli di stile utilizzati nell'HTML o utilizzando`addCssClassNamePrefix` Metodo per aggiungere un prefisso ai nomi delle classi CSS.

### D3: Esiste un modo per ottimizzare l'output HTML per la visualizzazione sul Web?
Sì, puoi ottimizzare l'output HTML per la visualizzazione sul Web configurando opzioni come l'esportazione dei font come Base64 e la conversione dei metafile in SVG.

### D4: Ci sono delle limitazioni quando si convertono documenti Word complessi in HTML?
Sebbene Aspose.Words per Java offra potenti capacità di conversione, i documenti Word complessi con layout intricati potrebbero richiedere un'ulteriore post-elaborazione per ottenere l'output HTML desiderato.
