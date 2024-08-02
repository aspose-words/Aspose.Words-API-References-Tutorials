---
title: Aggiungi filigrana di testo con opzioni specifiche
linktitle: Aggiungi filigrana di testo con opzioni specifiche
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere una filigrana di testo con opzioni specifiche ai tuoi documenti Word utilizzando Aspose.Words per .NET. Personalizza facilmente carattere, dimensione, colore e layout.
type: docs
weight: 10
url: /it/net/programming-with-watermark/add-text-watermark-with-specific-options/
---
## introduzione

Le filigrane possono essere un'aggiunta elegante e funzionale ai tuoi documenti Word, servendo a contrassegnare i documenti come riservati o ad aggiungere un tocco personalizzato. In questo tutorial esploreremo come aggiungere una filigrana di testo a un documento Word utilizzando Aspose.Words per .NET. Approfondiremo le opzioni specifiche che puoi configurare, come famiglia di caratteri, dimensione del carattere, colore e layout. Alla fine, sarai in grado di personalizzare la filigrana del tuo documento per adattarla alle tue esigenze. Quindi, prendi il tuo editor di codice e iniziamo!

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1.  Libreria Aspose.Words per .NET: avrai bisogno della libreria Aspose.Words installata. Se non lo hai già fatto, puoi scaricarlo dal file[Link per il download di Aspose.Words](https://releases.aspose.com/words/net/).
2. Comprensione di base di C#: questo tutorial utilizzerà C# come linguaggio di programmazione. Sarà utile una conoscenza fondamentale della sintassi C#.
3. Ambiente di sviluppo .NET: assicurati di avere un ambiente di sviluppo configurato (come Visual Studio) in cui puoi creare ed eseguire le tue applicazioni .NET.

## Importa spazi dei nomi

Per lavorare con Aspose.Words, dovrai includere gli spazi dei nomi necessari nel tuo progetto. Ecco cosa devi importare:

```csharp
using Aspose.Words;
using Aspose.Words.Rendering;
using System.Drawing;
```

## Passaggio 1: imposta il documento

 Innanzitutto, devi caricare il documento con cui vuoi lavorare. Per questo tutorial utilizzeremo un documento di esempio denominato`Document.docx`. Assicurati che questo documento esista nella directory specificata.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 In questo passaggio definisci la directory in cui si trova il tuo documento e caricalo in un'istanza del file`Document` classe.

## Passaggio 2: configura le opzioni della filigrana

Successivamente, configura le opzioni per la filigrana di testo. Puoi personalizzare vari aspetti, come la famiglia di caratteri, la dimensione del carattere, il colore e il layout. Impostiamo queste opzioni.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
    FontFamily = "Arial",
    FontSize = 36,
    Color = Color.Black,
    Layout = WatermarkLayout.Horizontal,
    IsSemitrasparent = false
};
```

Ecco cosa fa ciascuna opzione:
- `FontFamily`: specifica il carattere del testo della filigrana.
- `FontSize`: imposta la dimensione del testo della filigrana.
- `Color`: Definisce il colore del testo della filigrana.
- `Layout`Determina l'orientamento della filigrana (orizzontale o diagonale).
- `IsSemitrasparent`: imposta se la filigrana è semitrasparente.

## Passaggio 3: aggiungi il testo della filigrana

Ora applica la filigrana al tuo documento utilizzando le opzioni precedentemente configurate. In questo passaggio, imposterai il testo della filigrana su "Test" e applicherai le opzioni che hai definito.

```csharp
doc.Watermark.SetText("Test", options);
```

Questa riga di codice aggiunge la filigrana con il testo "Test" al documento, applicando le opzioni specificate.

## Passaggio 4: salva il documento

Infine, salva il documento con la nuova filigrana applicata. Puoi salvarlo con un nuovo nome per evitare di sovrascrivere il documento originale.

```csharp
doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

Questo frammento di codice salva il documento modificato nella stessa directory con un nuovo nome file.

## Conclusione

Aggiungere una filigrana di testo ai tuoi documenti Word utilizzando Aspose.Words per .NET è un processo semplice quando lo suddividi in passaggi gestibili. Seguendo questo tutorial, hai imparato come configurare varie opzioni della filigrana, tra cui carattere, dimensione, colore, layout e trasparenza. Con queste competenze, ora puoi personalizzare i tuoi documenti per soddisfare meglio le tue esigenze o includere informazioni essenziali come la riservatezza o il marchio.

 Se hai domande o hai bisogno di ulteriore assistenza, non esitare a consultare il[Documentazione Aspose.Words](https://reference.aspose.com/words/net/) oppure visitare il[Forum di supporto di Aspose](https://forum.aspose.com/c/words/8) per ulteriore aiuto.

## Domande frequenti

### Posso utilizzare caratteri diversi per la filigrana?

 Sì, puoi scegliere qualsiasi carattere installato sul tuo sistema specificando il file`FontFamily` proprietà nel`TextWatermarkOptions`.

### Come posso cambiare il colore della filigrana?

 È possibile modificare il colore della filigrana impostando il file`Color` proprietà nel`TextWatermarkOptions` a qualsiasi`System.Drawing.Color` valore.

### È possibile aggiungere più filigrane a un documento?

Aspose.Words supporta l'aggiunta di una filigrana alla volta. Per aggiungere più filigrane, dovrai crearle e applicarle in sequenza.

### Posso regolare la posizione della filigrana?

 IL`WatermarkLayout`La proprietà determina l'orientamento, ma le regolazioni precise del posizionamento non sono supportate direttamente. Potrebbe essere necessario utilizzare altre tecniche per il posizionamento esatto.

### Cosa succede se ho bisogno di una filigrana semitrasparente?

 Impostare il`IsSemitrasparent`proprietà a`true` per rendere semitrasparente la filigrana.