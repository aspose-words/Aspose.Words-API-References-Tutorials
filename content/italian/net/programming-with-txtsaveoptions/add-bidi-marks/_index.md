---
title: Aggiungi segni Bidi nel documento Word
linktitle: Aggiungi segni Bidi nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere segni bidirezionali (Bidi) nei documenti di Word utilizzando Aspose.Words per .NET con questa guida. Garantire la corretta direzione del testo per i contenuti multilingue.
type: docs
weight: 10
url: /it/net/programming-with-txtsaveoptions/add-bidi-marks/
---
## Introduzione

Nel mondo dell'elaborazione dei documenti, il testo bidirezionale (Bidi) può spesso essere un po' complicato da gestire. Ciò è particolarmente vero quando si ha a che fare con lingue con direzioni del testo diverse, come l'arabo o l'ebraico. Fortunatamente, Aspose.Words per .NET semplifica la gestione di tali scenari. In questo tutorial, spiegheremo come aggiungere segni Bidi a un documento Word utilizzando Aspose.Words per .NET.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere quanto segue:

1.  Aspose.Words per .NET: è necessario che sia installato Aspose.Words per .NET. Puoi scaricarlo da[Pagina dei download di Aspose](https://releases.aspose.com/words/net/).
2. .NET Framework o .NET Core: assicurati di disporre di un ambiente .NET compatibile configurato per l'esecuzione degli esempi.
3. Conoscenza di base di C#: familiarità con il linguaggio di programmazione C# e operazioni di base in .NET.

## Importa spazi dei nomi

Per iniziare, devi importare gli spazi dei nomi necessari. Ecco come puoi includerli nel tuo progetto:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Analizziamo il processo di aggiunta dei segni Bidi in un documento Word in passaggi chiari. Ogni passaggio ti guiderà attraverso il codice e il suo scopo.

## Passaggio 1: imposta il documento

 Inizia creando una nuova istanza di`Document` classe e a`DocumentBuilder` per aggiungere contenuto al documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea il documento e aggiungi contenuto
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 In questo passaggio inizializzi un nuovo documento Word e imposti un file`DocumentBuilder` per facilitare l'inserimento dei contenuti.

## Passaggio 2: aggiungi contenuto al tuo documento

Successivamente, aggiungi del testo al tuo documento. Qui aggiungeremo testo in diverse lingue per illustrare la gestione del testo Bidi.

```csharp
builder.Writeln("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder.Writeln("שלום עולם!");
builder.Writeln("مرحبا بالعالم!");
```

Qui aggiungiamo prima una frase inglese standard. Quindi, abilitiamo la formattazione del testo Bidi per il testo successivo, che è scritto in ebraico e arabo. Questo dimostra come incorporare il testo bidirezionale.

## Passaggio 3: configura le opzioni di salvataggio per Bidi Marks

 Per garantire che i segni Bidi vengano salvati correttamente nel documento, è necessario configurare il file`TxtSaveOptions` e abilitare il`AddBidiMarks` opzione.

```csharp
// Aggiungi segni Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

 In questo passaggio creiamo un'istanza di`TxtSaveOptions` e impostare il`AddBidiMarks`proprietà a`true`. Ciò garantisce che i contrassegni Bidi vengano inclusi quando si salva il documento come file di testo.

## Conclusione

L'aggiunta di segni Bidi ai tuoi documenti Word può essere un passaggio cruciale quando si ha a che fare con contenuti multilingue che includono lingue con diverse direzioni del testo. Con Aspose.Words per .NET, questo processo è semplice ed efficiente. Seguendo i passaggi sopra descritti, puoi assicurarti che i tuoi documenti rappresentino correttamente il testo Bidi, migliorandone la leggibilità e l'accuratezza.

## Domande frequenti

### Cosa sono i marchi Bidi e perché sono importanti?
I segni Bidi sono caratteri speciali utilizzati per controllare la direzione del testo nei documenti. Sono essenziali per visualizzare correttamente le lingue che si leggono da destra a sinistra, come l'arabo e l'ebraico.

### Posso utilizzare Aspose.Words per .NET per gestire altri tipi di problemi di direzione del testo?
Sì, Aspose.Words per .NET fornisce un supporto completo per varie esigenze di direzione e formattazione del testo, comprese le lingue da destra a sinistra e da sinistra a destra.

### È possibile applicare la formattazione Bidi solo a parti specifiche di un documento?
Sì, puoi applicare la formattazione Bidi a paragrafi o sezioni specifici del tuo documento secondo necessità.

### In quali formati posso salvare il documento con i contrassegni Bidi?
Nell'esempio fornito, il documento viene salvato come file di testo. Tuttavia, Aspose.Words supporta anche il salvataggio di documenti in vari formati preservando i segni Bidi.

### Dove posso trovare ulteriori informazioni su Aspose.Words per .NET?
 Puoi esplorare di più su Aspose.Words per .NET attraverso il[Richiedere documentazione](https://reference.aspose.com/words/net/) e accedi al[Forum di supporto](https://forum.aspose.com/c/words/8) per ulteriore aiuto.