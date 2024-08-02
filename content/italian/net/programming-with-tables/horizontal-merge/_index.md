---
title: Unione orizzontale
linktitle: Unione orizzontale
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come unire orizzontalmente le celle in un documento Word utilizzando Aspose.Words per .NET con questo tutorial dettagliato passo dopo passo.
type: docs
weight: 10
url: /it/net/programming-with-tables/horizontal-merge/
---
## introduzione

Ehilà! Pronto a tuffarti nel mondo di Aspose.Words per .NET? Oggi affronteremo una funzionalità estremamente utile: l'unione orizzontale delle tabelle. Potrebbe sembrare un po' tecnico, ma non preoccuparti, ti copro le spalle. Alla fine di questo tutorial sarai un professionista nell'unire le celle nei tuoi documenti Word a livello di codice. Allora rimbocchiamoci le maniche e cominciamo!

## Prerequisiti

Prima di passare al nocciolo della questione, ci sono alcune cose che dovrai avere a disposizione:

1. Libreria Aspose.Words per .NET: se non l'hai già fatto, scarica la libreria Aspose.Words per .NET. Puoi prenderlo[Qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: assicurati di disporre di un ambiente di sviluppo adatto, come Visual Studio.
3. Conoscenza di base di C#: una conoscenza di base della programmazione C# sarà utile.

Una volta che li hai ordinati, sei pronto per partire!

## Importa spazi dei nomi

Prima di immergerci nel codice, assicuriamoci di aver importato gli spazi dei nomi necessari. Nel tuo progetto C#, assicurati di includere:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Va bene, analizziamo il processo di unione orizzontale delle celle della tabella in un documento Word utilizzando Aspose.Words per .NET.

## Passaggio 1: impostazione del documento

 Per prima cosa, dobbiamo creare un nuovo documento Word e inizializzarlo`DocumentBuilder`:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Questo frammento di codice imposta un nuovo documento e prepara il file`DocumentBuilder` per azione.

## Passaggio 2: inserimento della prima cella

Successivamente, iniziamo inserendo la prima cella e contrassegnandola per l'unione orizzontale:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
```

 Qui inseriamo una nuova cella e la impostiamo`HorizontalMerge`proprietà a`CellMerge.First`, indicando che questa cella è l'inizio di una sequenza di celle unita.

## Passaggio 3: inserimento della cella unita

Adesso inseriamo la cella che verrà fusa con quella precedente:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
builder.EndRow();
```

 Questa cella è impostata per unirsi alla cella precedente utilizzando`CellMerge.Previous` . Nota come terminiamo la riga con`builder.EndRow()`.

## Passaggio 4: inserimento di celle non unite

Per illustrare la differenza, inseriamo un paio di celle non unite:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in one cell.");
builder.InsertCell();
builder.Write("Text in another cell.");
builder.EndRow();
```

Qui inseriamo due celle senza unione orizzontale. Questo mostra come si comportano le celle quando non fanno parte di una sequenza unita.

## Passaggio 5: finitura del tavolo

Infine, terminiamo la tabella e salviamo il documento:

```csharp
builder.EndTable();
doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

Questo frammento di codice completa la tabella e salva il documento nella directory specificata.

## Conclusione

E il gioco è fatto! Hai appena imparato l'arte di unire orizzontalmente le celle in un documento Word utilizzando Aspose.Words per .NET. Seguendo questi passaggi è possibile creare facilmente strutture di tabelle complesse. Continua a sperimentare ed esplorare le funzionalità di Aspose.Words per rendere i tuoi documenti dinamici e flessibili di cui hai bisogno. Buona programmazione!

## Domande frequenti

### Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una potente libreria che consente agli sviluppatori di creare, modificare e manipolare documenti Word a livello di codice nelle applicazioni .NET.

### Posso unire le celle verticalmente con Aspose.Words per .NET?
 Sì, puoi anche unire le celle verticalmente utilizzando il file`CellFormat.VerticalMerge` proprietà.

### Aspose.Words per .NET è gratuito?
 Aspose.Words per .NET offre una prova gratuita, ma per la piena funzionalità sarà necessario acquistare una licenza. Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).

### Come posso saperne di più su Aspose.Words per .NET?
 È possibile esplorare la documentazione dettagliata[Qui](https://reference.aspose.com/words/net/).

### Dove posso ottenere supporto per Aspose.Words per .NET?
 Per qualsiasi domanda o problema, puoi visitare il forum di supporto di Aspose[Qui](https://forum.aspose.com/c/words/8).