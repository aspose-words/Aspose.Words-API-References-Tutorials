---
title: Inserisci immagine mobile nel documento Word
linktitle: Inserisci immagine mobile nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un'immagine mobile in un documento Word utilizzando Aspose.Words per .NET con questa guida dettagliata passo passo. Perfetto per valorizzare i tuoi documenti.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-floating-image/
---
## Introduzione

Immagina di creare un report o una proposta straordinaria in cui le immagini sono perfettamente posizionate per completare il tuo testo. Con Aspose.Words per .NET, puoi raggiungere questo obiettivo senza sforzo. Questa libreria fornisce potenti funzionalità per la manipolazione dei documenti, rendendola una soluzione ideale per gli sviluppatori. In questo tutorial ci concentreremo sull'inserimento di un'immagine mobile utilizzando la classe DocumentBuilder. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questa guida ti guiderà attraverso ogni passaggio.

## Prerequisiti

Prima di approfondire, assicuriamoci di avere tutto il necessario per iniziare:

1.  Aspose.Words per .NET: puoi scaricare la libreria da[Pagina delle versioni di Aspose](https://releases.aspose.com/words/net/).
2. Visual Studio: qualsiasi versione che supporti lo sviluppo .NET.
3. Conoscenza di base di C#: sarà utile comprendere le basi della programmazione C#.
4. File immagine: un file immagine che desideri inserire, ad esempio un logo o un'immagine.

## Importa spazi dei nomi

Per utilizzare Aspose.Words nel tuo progetto, devi importare gli spazi dei nomi necessari. Questo viene fatto aggiungendo le seguenti righe nella parte superiore del file C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Con questi prerequisiti e spazi dei nomi a posto, siamo pronti per iniziare il nostro tutorial.

Analizziamo il processo di inserimento di un'immagine mobile in un documento di Word in passaggi gestibili. Ogni passaggio verrà spiegato in dettaglio per assicurarti di poterlo seguire senza intoppi.

## Passaggio 1: imposta il tuo progetto

Innanzitutto creare un nuovo progetto C# in Visual Studio. Puoi scegliere un'app console per semplicità.

1. Apri Visual Studio e crea un nuovo progetto.
2. Selezionare "App console (.NET Core)" e fare clic su "Avanti".
3. Dai un nome al tuo progetto e scegli una posizione in cui salvarlo. Fai clic su "Crea".
4. Installa Aspose.Words per .NET tramite NuGet Package Manager. Fai clic con il pulsante destro del mouse sul progetto in Esplora soluzioni, seleziona "Gestisci pacchetti NuGet" e cerca "Aspose.Words". Installa la versione più recente.

## Passaggio 2: inizializzare Document e DocumentBuilder

Ora che il tuo progetto è configurato, inizializziamo gli oggetti Document e DocumentBuilder.

1.  Crea una nuova istanza di`Document` classe:

```csharp
Document doc = new Document();
```

2. Inizializza un oggetto DocumentBuilder:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

 IL`Document` L'oggetto rappresenta il documento di Word e il file`DocumentBuilder` aiuta ad aggiungere contenuti ad esso.

## Passaggio 3: definire il percorso dell'immagine

Successivamente, specifica il percorso del file immagine. Assicurati che la tua immagine sia accessibile dalla directory del tuo progetto.

Definire la directory delle immagini e il nome del file immagine:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imagePath = dataDir + "Transparent background logo.png";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui è archiviata l'immagine.

## Passaggio 4: inserisci l'immagine mobile

Dopo aver impostato tutto, inseriamo l'immagine mobile nel documento.

 Usa il`InsertImage` metodo del`DocumentBuilder` classe per inserire l'immagine:

```csharp
builder.InsertImage(imagePath,
   RelativeHorizontalPosition.Margin,
   100,
   RelativeVerticalPosition.Margin,
   100,
   200,
   100,
   WrapType.Square);
```

Ecco cosa significa ciascun parametro:
- `imagePath`il percorso del file immagine.
- `RelativeHorizontalPosition.Margin`: La posizione orizzontale rispetto al margine.
- `100`: l'offset orizzontale dal margine (in punti).
- `RelativeVerticalPosition.Margin`: La posizione verticale rispetto al margine.
- `100`: l'offset verticale dal margine (in punti).
- `200`: La larghezza dell'immagine (in punti).
- `100`: L'altezza dell'immagine (in punti).
- `WrapType.Square`: lo stile del testo che avvolge l'immagine.

## Passaggio 5: salva il documento

Infine, salva il documento nella posizione desiderata.

1. Specificare il percorso del file di output:

```csharp
string outputPath = dataDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx";
```

2. Salvare il documento:

```csharp
doc.Save(outputPath);
```

Il tuo documento Word con l'immagine mobile è ora pronto!

## Conclusione

L'inserimento di un'immagine mobile in un documento Word utilizzando Aspose.Words per .NET è un processo semplice se suddiviso in passaggi gestibili. Seguendo questa guida, puoi aggiungere immagini dall'aspetto professionale ai tuoi documenti, migliorandone l'attrattiva visiva. Aspose.Words fornisce una solida API che rende la manipolazione dei documenti un gioco da ragazzi, sia che tu stia lavorando su report, proposte o qualsiasi altro tipo di documento.

## Domande frequenti

### Posso inserire più immagini utilizzando Aspose.Words per .NET?

 Sì, puoi inserire più immagini ripetendo l'operazione`InsertImage` metodo per ciascuna immagine con i parametri desiderati.

### Come posso cambiare la posizione dell'immagine?

 Puoi regolare il`RelativeHorizontalPosition`, `RelativeVerticalPosition`e parametri di offset per posizionare l'immagine secondo necessità.

### Quali altri tipi di avvolgimento sono disponibili per le immagini?

 Aspose.Words supporta vari tipi di wrap come`Inline`, `TopBottom`, `Tight`, `Through`e altro ancora. Puoi scegliere quello che meglio si adatta al layout del tuo documento.

### Posso utilizzare diversi formati di immagine?

Sì, Aspose.Words supporta un'ampia gamma di formati di immagine tra cui JPEG, PNG, BMP e GIF.

### Come posso ottenere una prova gratuita di Aspose.Words per .NET?

 Puoi ottenere una prova gratuita da[Aspose la pagina di prova gratuita](https://releases.aspose.com/).