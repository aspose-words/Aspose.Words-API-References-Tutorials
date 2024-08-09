---
title: Formato 1Bpp indicizzato
linktitle: Formato 1Bpp indicizzato
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come convertire un documento Word in un'immagine indicizzata da 1 Bpp utilizzando Aspose.Words per .NET. Segui la nostra guida passo passo per una facile conversione.
type: docs
weight: 10
url: /it/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
## Introduzione

Ti sei mai chiesto come salvare un documento Word come immagine in bianco e nero con solo poche righe di codice? Bene, sei fortunato! Oggi ci immergeremo in un piccolo trucchetto utilizzando Aspose.Words per .NET che ti consente di convertire i tuoi documenti in immagini indicizzate da 1 Bpp. Questo formato è perfetto per alcuni tipi di archiviazione digitale, stampa o quando è necessario risparmiare spazio. Analizzeremo ogni passaggio per renderlo facile come una torta. Pronti per iniziare? Immergiamoci!

## Prerequisiti

Prima di sporcarci le mani, ci sono alcune cose che devi avere a posto:

-  Aspose.Words per .NET: assicurati di avere la libreria installata. Puoi[scaricalo qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo .NET: Visual Studio è una buona opzione, ma puoi utilizzare qualsiasi ambiente con cui ti trovi a tuo agio.
- Conoscenza di base di C#: non preoccuparti, sarà semplice, ma un po' di familiarità con C# sarà utile.
- Un documento Word: tieni un documento Word di esempio pronto per essere convertito.

## Importa spazi dei nomi

Per prima cosa, dobbiamo importare gli spazi dei nomi necessari. Questo è fondamentale in quanto ci consente di accedere alle classi e ai metodi di cui abbiamo bisogno da Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Passaggio 1: imposta la directory dei documenti

Dovrai specificare il percorso della directory dei documenti. Qui è dove è archiviato il tuo documento Word e dove verrà salvata l'immagine convertita.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento Word

 Ora carichiamo il documento Word in un Aspose.Words`Document` oggetto. Questo oggetto rappresenta il tuo file Word e ti consente di manipolarlo.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passaggio 3: configura le opzioni di salvataggio dell'immagine

 Successivamente, dobbiamo impostare il file`ImageSaveOptions`È qui che avviene la magia. Lo configureremo per salvare l'immagine in formato PNG con modalità colore indicizzata 1Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1),
    ImageColorMode = ImageColorMode.BlackAndWhite,
    PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

- SaveFormat.Png: specifica che vogliamo salvare il documento come immagine PNG.
- PageSet(1): indica che stiamo convertendo solo la prima pagina.
- ImageColorMode.BlackAndWhite: imposta l'immagine in bianco e nero.
- ImagePixelFormat.Format1bppIndexed: imposta il formato dell'immagine su 1Bpp indicizzato.

## Passaggio 4: salva il documento come immagine

 Infine, salviamo il documento come immagine utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

## Conclusione

Ed ecco qua! Con solo poche righe di codice, hai trasformato il tuo documento Word in un'immagine indicizzata da 1 Bpp utilizzando Aspose.Words per .NET. Questo metodo è incredibilmente utile per creare immagini ad alto contrasto ed efficienti in termini di spazio dai tuoi documenti. Ora puoi integrarlo facilmente nei tuoi progetti e flussi di lavoro. Buona programmazione!

## Domande frequenti

### Che cos'è un'immagine indicizzata da 1 Bpp?
Un'immagine indicizzata 1Bpp (1 bit per pixel) è un formato immagine in bianco e nero in cui ogni pixel è rappresentato da un singolo bit, 0 o 1. Questo formato è molto efficiente in termini di spazio.

### Posso convertire più pagine di un documento Word contemporaneamente?
 Sì, puoi. Modifica il`PageSet` proprietà nel`ImageSaveOptions` per includere più pagine o l'intero documento.

### Ho bisogno di una licenza per utilizzare Aspose.Words per .NET?
 Sì, Aspose.Words per .NET richiede una licenza per la piena funzionalità. Puoi ottenere un[licenza temporanea qui](https://purchase.aspose.com/temporary-license/).

### In quali altri formati di immagine posso convertire il mio documento Word?
 Aspose.Words supporta vari formati di immagine tra cui JPEG, BMP e TIFF. Cambia semplicemente il`SaveFormat` nel`ImageSaveOptions`.

### Dove posso trovare ulteriore documentazione su Aspose.Words per .NET?
 È possibile trovare documentazione dettagliata su[Aspose.Words per la pagina della documentazione .NET](https://reference.aspose.com/words/net/).
