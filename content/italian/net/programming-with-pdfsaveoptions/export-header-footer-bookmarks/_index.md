---
title: Esporta i segnalibri del piè di pagina dell'intestazione del documento Word in un documento PDF
linktitle: Esporta i segnalibri del piè di pagina dell'intestazione del documento Word in un documento PDF
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come esportare i segnalibri di intestazione e piè di pagina da un documento Word in PDF utilizzando Aspose.Words per .NET con la nostra guida passo passo.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---
## Introduzione

Convertire documenti Word in PDF è un'attività comune, soprattutto quando desideri condividere o archiviare documenti preservandone la formattazione. A volte, questi documenti contengono segnalibri importanti nelle intestazioni e nei piè di pagina. In questo tutorial, esamineremo il processo di esportazione di questi segnalibri da un documento Word a un PDF utilizzando Aspose.Words per .NET.

## Prerequisiti

Prima di immergerci, assicurati di avere quanto segue:

- Aspose.Words per .NET: è necessario che sia installato Aspose.Words per .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: configura il tuo ambiente di sviluppo. È possibile utilizzare Visual Studio o qualsiasi altro IDE compatibile con .NET.
- Conoscenza di base di C#: è richiesta familiarità con la programmazione C# insieme agli esempi di codice.

## Importa spazi dei nomi

Per prima cosa, devi importare gli spazi dei nomi necessari nel tuo progetto C#. Aggiungi queste righe nella parte superiore del file di codice:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Suddividiamo il processo in passaggi facili da seguire.

## Passaggio 1: inizializzare il documento

Il primo passo è caricare il tuo documento Word. Ecco come puoi farlo:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

In questo passaggio, stai semplicemente specificando il percorso della directory dei documenti e caricando il documento Word.

## Passaggio 2: configura le opzioni di salvataggio del PDF

Successivamente, è necessario configurare le opzioni di salvataggio del PDF per garantire che i segnalibri nelle intestazioni e nei piè di pagina vengano esportati correttamente.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

 Qui stiamo configurando il`PdfSaveOptions` . IL`DefaultBookmarksOutlineLevel` imposta il livello di struttura per i segnalibri e il file`HeaderFooterBookmarksExportMode` La proprietà garantisce che venga esportata solo la prima occorrenza dei segnalibri nelle intestazioni e nei piè di pagina.

## Passaggio 3: salva il documento come PDF

Infine, salva il tuo documento come PDF con le opzioni configurate.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

In questo passaggio, stai salvando il documento nel percorso specificato con le opzioni che hai configurato.

## Conclusione

Ed ecco qua! Seguendo questi passaggi, puoi esportare facilmente i segnalibri dalle intestazioni e dai piè di pagina di un documento Word in un PDF utilizzando Aspose.Words per .NET. Questo metodo garantisce che importanti aiuti alla navigazione all'interno del documento vengano conservati nel formato PDF, semplificando la navigazione all'interno del documento per i lettori.

## Domande frequenti

### Posso esportare tutti i segnalibri dal documento Word in PDF?

 Sì, puoi. Nel`PdfSaveOptions`, puoi regolare le impostazioni per includere tutti i segnalibri, se necessario.

### Cosa succede se voglio esportare i segnalibri anche dal corpo del documento?

 È possibile configurare il`OutlineOptions` In`PdfSaveOptions` per includere segnalibri dal corpo del documento.

### È possibile personalizzare i livelli dei segnalibri nel PDF?

 Assolutamente! Puoi personalizzare il`DefaultBookmarksOutlineLevel` proprietà per impostare diversi livelli di struttura per i tuoi segnalibri.

### Come posso gestire i documenti senza segnalibri?

Se il tuo documento non ha segnalibri, il PDF verrà generato senza alcun contorno di segnalibri. Assicurati che il tuo documento contenga segnalibri se ne hai bisogno nel PDF.

### Posso utilizzare questo metodo per altri tipi di documenti come DOCX o RTF?

Sì, Aspose.Words per .NET supporta vari tipi di documenti, inclusi DOCX, RTF e altri.