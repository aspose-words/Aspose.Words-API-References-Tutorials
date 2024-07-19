---
title: Scollega intestazioni piè di pagina
linktitle: Scollega intestazioni piè di pagina
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come scollegare intestazioni e piè di pagina nei documenti di Word utilizzando Aspose.Words per .NET. Segui la nostra guida dettagliata passo dopo passo per padroneggiare la manipolazione dei documenti.
type: docs
weight: 10
url: /it/net/join-and-append-documents/unlink-headers-footers/
---
## introduzione

Nel mondo dell'elaborazione dei documenti, mantenere coerenti intestazioni e piè di pagina può talvolta rappresentare una sfida. Che tu stia unendo documenti o semplicemente cercando di avere intestazioni e piè di pagina diversi per sezioni diverse, sapere come scollegarli è essenziale. Oggi approfondiremo come ottenere questo risultato utilizzando Aspose.Words per .NET. Lo analizzeremo passo dopo passo in modo che tu possa seguirlo facilmente. Pronto a padroneggiare la manipolazione dei documenti? Iniziamo!

## Prerequisiti

Prima di addentrarci nel nocciolo della questione, ci sono alcune cose di cui avrai bisogno:

-  Aspose.Words per .NET Library: puoi scaricarlo dal file[Pagina delle versioni di Aspose](https://releases.aspose.com/words/net/).
- .NET Framework: assicurati di avere installato un .NET Framework compatibile.
- IDE: Visual Studio o qualsiasi altro ambiente di sviluppo integrato compatibile con .NET.
- Comprensione di base di C#: avrai bisogno di una conoscenza di base del linguaggio di programmazione C#.

## Importa spazi dei nomi

Per iniziare, assicurati di importare gli spazi dei nomi necessari nel tuo progetto. Ciò ti consentirà di accedere alla libreria Aspose.Words e alle sue funzionalità.

```csharp
using Aspose.Words;
```

Analizziamo il processo in passaggi gestibili per aiutarti a scollegare intestazioni e piè di pagina nei tuoi documenti Word.

## Passaggio 1: imposta il tuo progetto

Innanzitutto, dovrai configurare l'ambiente del tuo progetto. Apri il tuo IDE e crea un nuovo progetto .NET. Aggiungi un riferimento alla libreria Aspose.Words scaricata in precedenza.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento di origine

Successivamente, devi caricare il documento sorgente che desideri modificare. Questo documento avrà le sue intestazioni e piè di pagina scollegati.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## Passaggio 3: caricare il documento di destinazione

Ora carica il documento di destinazione a cui aggiungerai il documento di origine dopo aver scollegato le sue intestazioni e piè di pagina.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 4: scollega intestazioni e piè di pagina

 Questo passaggio è cruciale. Per scollegare le intestazioni e i piè di pagina del documento di origine da quelli del documento di destinazione, utilizzerai il file`LinkToPrevious` metodo. Questo metodo garantisce che le intestazioni e i piè di pagina non vengano trasferiti nel documento allegato.

```csharp
// Scollega le intestazioni e i piè di pagina nel documento di origine per interrompere questo problema
//dal continuare le intestazioni e i piè di pagina del documento di destinazione.
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Passaggio 5: aggiungi il documento di origine

 Dopo aver scollegato intestazioni e piè di pagina, puoi aggiungere il documento di origine al documento di destinazione. Usa il`AppendDocument` metodo e impostare la modalità del formato di importazione su`KeepSourceFormatting` per mantenere la formattazione originale del documento di origine.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 6: salvare il documento finale

Infine, salva il documento appena creato. Questo documento avrà il contenuto del documento di origine aggiunto al documento di destinazione, con intestazioni e piè di pagina scollegati.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

## Conclusione

E il gioco è fatto! Seguendo questi passaggi, hai scollegato con successo le intestazioni e i piè di pagina nel documento di origine e li hai aggiunti al documento di destinazione utilizzando Aspose.Words per .NET. Questa tecnica può essere particolarmente utile quando lavori con documenti complessi che richiedono intestazioni e piè di pagina diversi per sezioni diverse. Buona programmazione!

## Domande frequenti

### Cos'è Aspose.Words per .NET?  
Aspose.Words per .NET è una potente libreria per lavorare con documenti Word nelle applicazioni .NET. Consente agli sviluppatori di creare, modificare, convertire e stampare documenti a livello di codice.

### Posso scollegare intestazioni e piè di pagina solo per sezioni specifiche?  
 Sì, puoi scollegare intestazioni e piè di pagina per sezioni specifiche accedendo a`HeadersFooters` proprietà della sezione desiderata e utilizzando il file`LinkToPrevious` metodo.

### È possibile mantenere la formattazione originale del documento sorgente?  
 Sì, quando aggiungi il documento sorgente, usa il file`ImportFormatMode.KeepSourceFormatting` opzione per mantenere la formattazione originale.

### Posso utilizzare Aspose.Words per .NET con altri linguaggi .NET oltre a C#?  
Assolutamente! Aspose.Words per .NET può essere utilizzato con qualsiasi linguaggio .NET, inclusi VB.NET e F#.

### Dove posso trovare ulteriore documentazione e supporto per Aspose.Words per .NET?  
 È possibile trovare una documentazione completa su[Aspose.Words per la pagina della documentazione .NET](https://reference.aspose.com/words/net/) e il supporto è disponibile su[Aspose forum](https://forum.aspose.com/c/words/8).
