---
title: Riduci le dimensioni del PDF con i caratteri Wmf ridimensionati alle dimensioni del metafile
linktitle: Riduci le dimensioni del PDF con i caratteri Wmf ridimensionati alle dimensioni del metafile
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per ridurre le dimensioni del PDF con i caratteri wmf ridimensionati alle dimensioni del metafile durante la conversione in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---
## introduzione

Quando si lavora con file PDF, in particolare quelli generati da documenti Word contenenti grafica WMF (Windows Metafile), la gestione delle dimensioni può diventare un aspetto cruciale della gestione dei documenti. Un modo per controllare la dimensione del PDF è regolare il modo in cui i caratteri WMF vengono visualizzati all'interno del documento. In questo tutorial, esploreremo come ridurre le dimensioni del PDF ridimensionando i caratteri WMF alla dimensione del metafile utilizzando Aspose.Words per .NET.

## Prerequisiti

Prima di addentrarti nei passaggi, assicurati di avere quanto segue:

1. Aspose.Words per .NET: assicurati di avere la libreria Aspose.Words installata. In caso contrario, puoi[scaricalo qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: questa esercitazione presuppone che tu abbia configurato un ambiente di sviluppo .NET (come Visual Studio) in cui puoi scrivere ed eseguire codice C#.
3. Comprensione di base della programmazione .NET: sarà utile la familiarità con i concetti di base della programmazione .NET e la sintassi C#.
4. Documento Word con grafica WMF: avrai bisogno di un documento Word contenente grafica WMF. Puoi utilizzare il tuo documento o crearne uno per i test.

## Importa spazi dei nomi

Innanzitutto, devi importare gli spazi dei nomi necessari nel tuo progetto C#. Questo ti darà accesso alle classi e ai metodi necessari per lavorare con Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Passaggio 1: caricare il documento Word

 Per iniziare, carica il documento Word che contiene la grafica WMF. Questo viene fatto utilizzando il`Document` classe da Aspose.Words.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Caricare il documento
Document doc = new Document(dataDir + "WMF with text.docx");
```

 Qui,`dataDir` è un segnaposto per il percorso della directory dei documenti. Creiamo un'istanza di`Document` class passando il percorso del file Word. Questo carica il documento in memoria, pronto per ulteriori elaborazioni.

## Passaggio 2: configurare le opzioni di rendering del metafile

 Successivamente, è necessario configurare le opzioni di rendering del metafile. Nello specifico, imposta il`ScaleWmfFontsToMetafileSize`proprietà a`false`. Controlla se i caratteri WMF vengono ridimensionati per corrispondere alla dimensione del metafile.

```csharp
// Crea una nuova istanza di MetafileRenderingOptions
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
    ScaleWmfFontsToMetafileSize = false
};
```

 IL`MetafileRenderingOptions` fornisce opzioni su come vengono visualizzati i metafile (come WMF). IMPOSTANDO`ScaleWmfFontsToMetafileSize` A`false`, stai indicando ad Aspose.Words di non ridimensionare i caratteri in base alla dimensione del metafile, il che può aiutare a ridurre la dimensione complessiva del PDF.

## Passaggio 3: imposta le opzioni di salvataggio del PDF

Ora configura le opzioni di salvataggio del PDF per utilizzare le opzioni di rendering del metafile che hai appena impostato. Questo indica ad Aspose.Words come gestire i metafile quando si salva il documento come PDF.

```csharp
// Crea una nuova istanza di PdfSaveOptions
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    MetafileRenderingOptions = metafileRenderingOptions
};
```

 IL`PdfSaveOptions` class consente di specificare varie impostazioni per salvare il documento come PDF. Assegnando quanto precedentemente configurato`MetafileRenderingOptions` al`MetafileRenderingOptions` proprietà di`PdfSaveOptions`, ti assicuri che il documento venga salvato in base alle impostazioni di rendering del metafile desiderate.

## Passaggio 4: salva il documento come PDF

Infine, salva il documento Word come PDF utilizzando le opzioni di salvataggio configurate. Ciò applicherà tutte le impostazioni, comprese le opzioni di rendering del metafile, al PDF di output.


```csharp
// Salva il documento come PDF
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

 In questo passaggio, il`Save` metodo del`Document` viene utilizzata per esportare il documento in un file PDF. Viene specificato il percorso in cui verrà salvato il PDF, insieme al file`PdfSaveOptions` che includono le impostazioni di rendering del metafile.

## Conclusione

Ridimensionando i caratteri WMF alla dimensione del metafile, puoi ridurre significativamente la dimensione dei file PDF generati da documenti Word. Questa tecnica aiuta a ottimizzare l'archiviazione e la distribuzione dei documenti senza compromettere la qualità del contenuto visivo. Seguendo i passaggi sopra descritti garantirai che i tuoi file PDF siano più gestibili ed efficienti in termini di dimensioni.

## Domande frequenti

### Cos'è WMF e perché è importante per le dimensioni del PDF?

WMF (Windows Metafile) è un formato grafico utilizzato in Microsoft Windows. Può contenere sia dati vettoriali che bitmap. Poiché i dati vettoriali possono essere ridimensionati e manipolati, è importante gestirli correttamente per evitare file PDF inutilmente grandi.

### In che modo il ridimensionamento dei caratteri WMF in base alle dimensioni del metafile influisce sul PDF?

Il ridimensionamento dei caratteri WMF in base alle dimensioni del metafile può aiutare a ridurre le dimensioni complessive del PDF evitando il rendering dei caratteri ad alta risoluzione che potrebbe aumentare le dimensioni del file.

### Posso utilizzare altri formati di metafile con Aspose.Words?

Sì, Aspose.Words supporta vari formati di metafile, incluso EMF (Enhanced Metafile) oltre a WMF.

### Questa tecnica è applicabile a tutti i tipi di documenti Word?

Sì, questa tecnica può essere applicata a qualsiasi documento Word che contenga grafica WMF, aiutando a ottimizzare la dimensione del PDF generato.

### Dove posso trovare ulteriori informazioni su Aspose.Words?

 Puoi esplorare di più su Aspose.Words nel[Documentazione Aspose.Words](https://reference.aspose.com/words/net/) . Per download, prove e supporto, visitare il sito[Pagina di download di Aspose.Words](https://releases.aspose.com/words/net/), [Acquista Aspose.Words](https://purchase.aspose.com/buy), [Prova gratuita](https://releases.aspose.com/), [Licenza temporanea](https://purchase.aspose.com/temporary-license/) , E[Supporto](https://forum.aspose.com/c/words/8).