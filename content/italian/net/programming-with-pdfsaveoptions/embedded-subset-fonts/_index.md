---
title: Incorpora caratteri sottoinsieme nel documento PDF
linktitle: Incorpora caratteri sottoinsieme nel documento PDF
second_title: API di elaborazione dei documenti Aspose.Words
description: Riduci le dimensioni del file PDF incorporando solo i sottoinsiemi di caratteri necessari utilizzando Aspose.Words per .NET. Segui la nostra guida passo passo per ottimizzare i tuoi PDF in modo efficiente.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---
## introduzione

Hai mai notato come alcuni file PDF siano molto più grandi di altri, anche quando contengono contenuti simili? Il colpevole spesso risiede nei caratteri. Incorporare i caratteri in un PDF garantisce che abbia lo stesso aspetto su qualsiasi dispositivo, ma può anche aumentare le dimensioni del file. Fortunatamente, Aspose.Words per .NET offre una pratica funzionalità per incorporare solo i sottoinsiemi di caratteri necessari, mantenendo i tuoi PDF snelli ed efficienti. Questo tutorial ti guiderà attraverso il processo, passo dopo passo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

-  Aspose.Words per .NET: puoi scaricarlo[Qui](https://releases.aspose.com/words/net/).
- Ambiente .NET: assicurati di disporre di un ambiente di sviluppo .NET funzionante.
- Conoscenza di base di C#: la familiarità con la programmazione C# ti aiuterà a proseguire.

## Importa spazi dei nomi

Per utilizzare Aspose.Words per .NET, è necessario importare gli spazi dei nomi necessari nel progetto. Aggiungi questi nella parte superiore del tuo file C#:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Passaggio 1: caricare il documento

 Per prima cosa dobbiamo caricare il documento Word che vogliamo convertire in PDF. Questo viene fatto utilizzando il`Document` classe fornita da Aspose.Words.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Questo frammento di codice carica il documento che si trova in`dataDir` . Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo del documento.

## Passaggio 2: configura le opzioni di salvataggio del PDF

 Successivamente, configuriamo il`PdfSaveOptions` per garantire che vengano incorporati solo i sottoinsiemi di caratteri necessari. IMPOSTANDO`EmbedFullFonts` A`false`, diciamo ad Aspose.Words di incorporare solo i glifi utilizzati nel documento.

```csharp
// Il PDF di output conterrà sottoinsiemi di caratteri nel documento.
// Solo i glifi utilizzati nel documento sono inclusi nei caratteri PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

Questo piccolo ma cruciale passaggio aiuta a ridurre significativamente le dimensioni del file PDF.

## Passaggio 3: salva il documento come PDF

 Infine, salviamo il documento come PDF utilizzando il file`Save` metodo, applicando il configurato`PdfSaveOptions`.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf", saveOptions);
```

 Questo codice genererà un file PDF con il nome`WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf` nella directory specificata, con incorporati solo i sottoinsiemi di caratteri necessari.

## Conclusione

il gioco è fatto! Seguendo questi semplici passaggi, puoi ridurre in modo efficiente la dimensione dei tuoi file PDF incorporando solo i sottoinsiemi di caratteri necessari utilizzando Aspose.Words per .NET. Ciò non solo consente di risparmiare spazio di archiviazione, ma garantisce anche tempi di caricamento più rapidi e prestazioni migliori, soprattutto per i documenti con caratteri estesi.

## Domande frequenti

### Perché dovrei incorporare solo sottoinsiemi di caratteri in un PDF?
Incorporando solo i sottoinsiemi di caratteri necessari è possibile ridurre significativamente le dimensioni del file PDF senza compromettere l'aspetto e la leggibilità del documento.

### Posso ripristinare l'incorporamento dei caratteri completi, se necessario?
 Si, puoi. Basta impostare il`EmbedFullFonts`proprietà a`true` nel`PdfSaveOptions`.

### Aspose.Words per .NET supporta altre funzionalità di ottimizzazione dei PDF?
Assolutamente! Aspose.Words per .NET offre una gamma di opzioni per l'ottimizzazione dei PDF, inclusa la compressione delle immagini e la rimozione di oggetti inutilizzati.

### Quali tipi di caratteri possono essere incorporati in sottoinsiemi utilizzando Aspose.Words per .NET?
Aspose.Words per .NET supporta l'incorporamento di sottoinsiemi per tutti i caratteri TrueType utilizzati nel documento.

### Come posso verificare quali caratteri sono incorporati nel mio PDF?
Puoi aprire il PDF in Adobe Acrobat Reader e controllare le proprietà nella scheda Caratteri per vedere i caratteri incorporati.
