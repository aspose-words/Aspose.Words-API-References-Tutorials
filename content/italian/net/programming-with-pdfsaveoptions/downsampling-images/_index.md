---
title: Riduci le dimensioni del documento PDF con il downsampling delle immagini
linktitle: Riduci le dimensioni del documento PDF con il downsampling delle immagini
second_title: API di elaborazione dei documenti Aspose.Words
description: Riduci le dimensioni del documento PDF riducendo le immagini utilizzando Aspose.Words per .NET. Ottimizza i tuoi PDF per tempi di caricamento e download più rapidi.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/downsampling-images/
---
## introduzione

PDF sono un punto fermo nel mondo digitale, utilizzati per qualsiasi cosa, dalla condivisione di documenti alla creazione di eBook. Tuttavia, le loro dimensioni a volte possono rappresentare un ostacolo, soprattutto quando si ha a che fare con contenuti ricchi di immagini. È qui che entra in gioco il downsampling delle immagini. Riducendo la risoluzione delle immagini all'interno del PDF, puoi ridurre significativamente le dimensioni del file senza compromettere troppo la qualità. In questo tutorial, esamineremo i passaggi per raggiungere questo obiettivo utilizzando Aspose.Words per .NET.

## Prerequisiti

Prima di addentrarci nel codice, assicuriamoci di avere tutto ciò di cui hai bisogno:

1.  Aspose.Words per .NET: assicurati di avere la libreria Aspose.Words installata. In caso contrario, puoi scaricarlo[Qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: qualsiasi ambiente di sviluppo .NET come Visual Studio.
3. Conoscenza di base di C#: sarà utile comprendere le basi della programmazione C#.
4.  Un documento di esempio: un documento Word (ad esempio,`Rendering.docx`) con immagini da convertire in PDF.

## Importa spazi dei nomi

Per prima cosa, devi importare gli spazi dei nomi necessari. Aggiungi questi nella parte superiore del file di codice:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Ora suddividiamo il processo in passaggi gestibili.

## Passaggio 1: caricare il documento

Il primo passo è caricare il tuo documento Word. Qui è dove specifichi il percorso della directory dei documenti.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

In questo passaggio, stiamo caricando il documento Word dalla directory specificata. Assicurati di sostituire`"YOUR DOCUMENT DIRECTORY"`con il percorso effettivo in cui si trova il documento.

## Passaggio 2: configura le opzioni di downsampling

Successivamente, dobbiamo configurare le opzioni di downsampling. Ciò comporta l'impostazione della risoluzione e della soglia di risoluzione per le immagini.

```csharp
// Possiamo impostare una soglia minima per il downsampling.
// Questo valore impedirà il downsampling della seconda immagine nel documento di input.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 Qui stiamo creando una nuova istanza di`PdfSaveOptions` e impostando il`Resolution` a 36 DPI e il`ResolutionThreshold` a 128 DPI. Ciò significa che qualsiasi immagine con una risoluzione superiore a 128 DPI verrà sottocampionata a 36 DPI.

## Passaggio 3: salva il documento come PDF

Infine, salviamo il documento come PDF con le opzioni configurate.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

In questo passaggio finale, salviamo il documento come PDF nella stessa directory con le opzioni di downsampling specificate.

## Conclusione

il gioco è fatto! Hai ridotto con successo le dimensioni del tuo PDF riducendo le immagini utilizzando Aspose.Words per .NET. Ciò non solo rende i tuoi PDF più gestibili, ma aiuta anche a caricare e scaricare più velocemente ed esperienze di visualizzazione più fluide.

## Domande frequenti

### Cos'è il downsampling?
Il downsampling è il processo di riduzione della risoluzione delle immagini, che aiuta a ridurre le dimensioni del file dei documenti contenenti tali immagini.

### Il downsampling influirà sulla qualità delle immagini?
Sì, il downsampling ridurrà la qualità dell'immagine. Tuttavia, l’impatto dipende dal grado di riduzione della risoluzione. È un compromesso tra dimensione del file e qualità dell'immagine.

### Posso scegliere quali immagini sottocampionare?
 Sì, impostando il`ResolutionThreshold`, puoi controllare quali immagini vengono sottocampionate in base alla loro risoluzione originale.

### Qual è la risoluzione ideale per il downsampling?
La risoluzione ideale dipende dalle vostre specifiche esigenze. Comunemente, per le immagini web vengono utilizzate 72 DPI, mentre per la qualità di stampa vengono utilizzate risoluzioni più elevate.

### Aspose.Words per .NET è gratuito?
 Aspose.Words per .NET è un prodotto commerciale, ma puoi scaricare una versione di prova gratuita[Qui](https://releases.aspose.com/) o richiedere un[licenza temporanea](https://purchase.aspose.com/temporary-license/).