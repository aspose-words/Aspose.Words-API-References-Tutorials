---
title: Rimuovi i piè di pagina delle intestazioni della fonte
linktitle: Rimuovi i piè di pagina delle intestazioni della fonte
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come rimuovere intestazioni e piè di pagina nei documenti di Word utilizzando Aspose.Words per .NET. Semplifica la gestione dei tuoi documenti con la nostra guida passo passo.
type: docs
weight: 10
url: /it/net/join-and-append-documents/remove-source-headers-footers/
---
## introduzione

In questa guida completa, approfondiremo come rimuovere in modo efficace intestazioni e piè di pagina da un documento Word utilizzando Aspose.Words per .NET. Intestazioni e piè di pagina vengono comunemente utilizzati per la numerazione delle pagine, i titoli dei documenti o altri contenuti ripetuti nei documenti di Word. Che tu stia unendo documenti o ripulendo la formattazione, padroneggiare questo processo può semplificare le attività di gestione dei documenti. Esploriamo il processo passo passo per raggiungere questo obiettivo utilizzando Aspose.Words per .NET.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di aver impostato i seguenti prerequisiti:

1. Ambiente di sviluppo: avere installato Visual Studio o qualsiasi altro ambiente di sviluppo .NET.
2.  Aspose.Words per .NET: assicurati di aver scaricato e installato Aspose.Words per .NET. In caso contrario, puoi ottenerlo da[Qui](https://releases.aspose.com/words/net/).
3. Conoscenze di base: familiarità con la programmazione C# e le nozioni di base del framework .NET.

## Importa spazi dei nomi

Prima di iniziare a scrivere codice, assicurati di importare gli spazi dei nomi necessari nel file C#:

```csharp
using Aspose.Words;
```

## Passaggio 1: caricare il documento di origine

 Innanzitutto, devi caricare il documento di origine da cui desideri rimuovere intestazioni e piè di pagina. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti in cui si trova il documento di origine.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## Passaggio 2: crea o carica il documento di destinazione

 Se non hai già creato un documento di destinazione in cui desideri inserire il contenuto modificato, puoi crearne uno nuovo`Document` oggetto o caricarne uno esistente.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: cancella intestazioni e piè di pagina dalle sezioni

Scorrere ogni sezione del documento di origine (`srcDoc`) e cancellarne le intestazioni e i piè di pagina.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Passaggio 4: gestisci l'impostazione LinkToPrevious

Per impedire che intestazioni e piè di pagina continuino nel documento di destinazione (`dstDoc` ), assicurarsi che`LinkToPrevious` l'impostazione per intestazioni e piè di pagina è impostata su`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Passaggio 5: aggiungi il documento modificato al documento di destinazione

Infine, aggiungi il contenuto modificato dal documento di origine (`srcDoc`) al documento di destinazione (`dstDoc`) mantenendo la formattazione originale.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 6: salvare il documento risultante

Salva il documento finale con intestazioni e piè di pagina rimossi nella directory specificata.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

## Conclusione

Rimuovere intestazioni e piè di pagina da un documento Word utilizzando Aspose.Words per .NET è un processo semplice che può migliorare notevolmente le attività di gestione dei documenti. Seguendo i passaggi sopra descritti, puoi ripulire in modo efficiente i documenti per un aspetto raffinato e professionale.

## Domande frequenti

### Posso rimuovere intestazioni e piè di pagina solo da sezioni specifiche?
Sì, puoi scorrere le sezioni e cancellare selettivamente intestazioni e piè di pagina secondo necessità.

### Aspose.Words per .NET supporta la rimozione di intestazioni e piè di pagina su più documenti?
Assolutamente, puoi manipolare intestazioni e piè di pagina su più documenti utilizzando Aspose.Words per .NET.

###  Cosa succede se dimentico di impostare?`LinkToPrevious` to `false`?
Le intestazioni e i piè di pagina del documento di origine possono continuare nel documento di destinazione.

### Posso rimuovere intestazioni e piè di pagina a livello di codice senza influire su altre formattazioni?
Sì, Aspose.Words per .NET ti consente di rimuovere intestazioni e piè di pagina preservando il resto della formattazione del documento.

### Dove posso trovare ulteriori risorse e supporto per Aspose.Words per .NET?
 Visitare il[Aspose.Words per la documentazione .NET](https://reference.aspose.com/words/net/) per riferimenti ed esempi API dettagliati.
