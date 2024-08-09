---
title: Inserisci forma
linktitle: Inserisci forma
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire e manipolare forme nei documenti Word utilizzando Aspose.Words per .NET con la nostra guida passo passo.
type: docs
weight: 10
url: /it/net/programming-with-shapes/insert-shape/
---
## Introduzione

Quando si tratta di creare documenti Word visivamente accattivanti e ben strutturati, le forme possono svolgere un ruolo fondamentale. Che tu stia aggiungendo frecce, riquadri o anche forme personalizzate complesse, la capacità di manipolare questi elementi a livello di codice offre una flessibilità senza pari. In questo tutorial esploreremo come inserire e manipolare forme nei documenti di Word utilizzando Aspose.Words per .NET.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:

1.  Aspose.Words per .NET: scarica e installa la versione più recente da[Pagina delle versioni di Aspose](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: un ambiente di sviluppo .NET adatto come Visual Studio.
3. Conoscenza di base di C#: Familiarità con il linguaggio di programmazione C# e concetti di base.

## Importa spazi dei nomi

Per iniziare, dovrai importare gli spazi dei nomi necessari nel tuo progetto C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Passaggio 1: imposta il tuo progetto

Prima di poter iniziare a inserire forme, è necessario impostare il progetto e aggiungere la libreria Aspose.Words per .NET.

1. Crea un nuovo progetto: apri Visual Studio e crea un nuovo progetto di applicazione console C#.
2. Aggiungi Aspose.Words per .NET: installa la libreria Aspose.Words per .NET tramite NuGet Package Manager.

```bash
Install-Package Aspose.Words
```

## Passaggio 2: inizializzare il documento

Per prima cosa dovrai inizializzare un nuovo documento e un generatore di documenti, che ti aiuterà a costruire il documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inizializza un nuovo documento
Document doc = new Document();

// Inizializza un DocumentBuilder per facilitare la creazione del documento
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserisci una forma

Ora inseriamo una forma nel documento. Inizieremo aggiungendo una semplice casella di testo.

```csharp
// Inserisci una forma di casella di testo nel documento
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100, RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// Ruota la forma
shape.Rotation = 30.0;
```

In questo esempio inseriamo una casella di testo nella posizione (100, 100) con una larghezza e un'altezza di 50 unità ciascuna. Ruotiamo anche la forma di 30 gradi.

## Passaggio 4: aggiungi un'altra forma

Aggiungiamo un'altra forma al documento, questa volta senza specificare la posizione.

```csharp
// Aggiungi un'altra forma di casella di testo
Shape secondShape = builder.InsertShape(ShapeType.TextBox, 50, 50);

// Ruota la forma
secondShape.Rotation = 30.0;
```

Questo frammento di codice inserisce un'altra casella di testo con le stesse dimensioni e rotazione della prima ma senza specificarne la posizione.

## Passaggio 5: salva il documento

 Dopo aver aggiunto le forme, il passaggio finale è salvare il documento. Utilizzeremo il`OoxmlSaveOptions` per specificare il formato di salvataggio.

```csharp
// Definire le opzioni di salvataggio in conformità
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};

// Salva il documento
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## Conclusione

Ed ecco qua! Hai inserito e manipolato con successo forme in un documento Word utilizzando Aspose.Words per .NET. Questo tutorial ha trattato le nozioni di base, ma Aspose.Words offre molte funzionalità più avanzate per lavorare con le forme, come stili personalizzati, connettori e forme di gruppo.

 Per informazioni più dettagliate, visitare il[Aspose.Words per la documentazione .NET](https://reference.aspose.com/words/net/).

## Domande frequenti

### Come inserisco diversi tipi di forme?
Puoi cambiare il`ShapeType` nel`InsertShape` metodo per inserire diversi tipi di forme come cerchi, rettangoli e frecce.

### Posso aggiungere testo all'interno delle forme?
 Sì, puoi usare il`builder.Write` metodo per aggiungere testo all'interno delle forme dopo averle inserite.

### È possibile modellare le forme?
 Sì, puoi modellare le forme impostando proprietà come`FillColor`, `StrokeColor` , E`StrokeWeight`.

### Come posso posizionare le forme rispetto ad altri elementi?
 Usa il`RelativeHorizontalPosition`E`RelativeVerticalPosition` proprietà per posizionare le forme rispetto ad altri elementi nel documento.

### Posso raggruppare più forme insieme?
 Sì, Aspose.Words per .NET ti consente di raggruppare forme utilizzando il file`GroupShape` classe.