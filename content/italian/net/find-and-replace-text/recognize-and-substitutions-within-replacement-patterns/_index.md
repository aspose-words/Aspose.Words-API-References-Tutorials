---
title: Riconoscere e sostituzioni all'interno dei modelli di sostituzione
linktitle: Riconoscere e sostituzioni all'interno dei modelli di sostituzione
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare i modelli di sostituzione con riconoscimenti e sostituzioni in Aspose.Words per .NET per manipolare documenti Word.
type: docs
weight: 10
url: /it/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

In questo articolo, esploreremo il codice sorgente C# sopra riportato per comprendere come utilizzare la funzione Riconosci e sostituzioni all'interno dei modelli di sostituzione nella libreria Aspose.Words per .NET. Questa funzionalità aiuta a riconoscere modelli di ricerca complessi ed eseguire sostituzioni in base ai gruppi acquisiti durante la manipolazione del documento.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione di un nuovo documento

Prima di iniziare a utilizzare corrispondenze e sostituzioni nei modelli di sostituzione, dobbiamo creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto:

```csharp
Document doc = new Document();
```

## Passaggio 2: inserisci il testo nel documento

 Una volta che abbiamo un documento, possiamo inserire del testo usando a`DocumentBuilder` oggetto. Nel nostro esempio, stiamo utilizzando il file`Write` metodo per inserire la frase "Jason dà a Paul dei soldi". :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Fase 3: Riconoscimenti e sostituzioni nei modelli di sostituzione

 Ora useremo il`Range.Replace` funzione per eseguire la ricerca e la sostituzione del testo utilizzando un'espressione regolare per riconoscere modelli specifici. Nel nostro esempio utilizziamo l'espressione regolare`([A-z]+) gives money to ([A-z]+)` riconoscere le frasi in cui qualcuno dà soldi a qualcun altro. Usiamo il modello di sostituzione`$2 takes money from $1` effettuare la sostituzione invertendo i ruoli. L'impiego di`$1` E`$2` si riferisce ai gruppi catturati dall'espressione regolare:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Codice sorgente di esempio per il riconoscimento e le sostituzioni all'interno dei modelli di sostituzione utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per illustrare l'uso di corrispondenze e sostituzioni nei modelli di sostituzione con Aspose.Words per .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per comprendere come utilizzare la funzionalità Riconosci e sostituzioni all'interno dei modelli di sostituzione di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per creare un documento, inserire testo, eseguire ricerche e sostituire utilizzando espressioni regolari e modelli di sostituzione basati su gruppi acquisiti e manipolare il documento.

### Domande frequenti

#### D: Qual è la funzionalità "Riconosci e sostituzioni all'interno dei modelli di sostituzione" in Aspose.Words per .NET?

R: La funzionalità "Riconosci e sostituzioni all'interno di modelli di sostituzione" in Aspose.Words per .NET consente di riconoscere modelli di ricerca complessi utilizzando espressioni regolari ed eseguire sostituzioni in base ai gruppi acquisiti durante la manipolazione del documento. Ti consente di trasformare dinamicamente il testo corrispondente facendo riferimento ai gruppi acquisiti nel modello di sostituzione.

#### D: Come posso creare un nuovo documento utilizzando Aspose.Words per .NET?

 R: Per creare un nuovo documento utilizzando Aspose.Words per .NET, puoi creare un'istanza di a`Document` oggetto. Ecco un esempio di codice C# per creare un nuovo documento:

```csharp
Document doc = new Document();
```

#### D: Come posso inserire testo in un documento utilizzando Aspose.Words per .NET?

 R: Una volta che hai un documento, puoi inserire del testo usando a`DocumentBuilder` oggetto. Ad esempio, per inserire la frase "Jason dà soldi a Paul.", puoi utilizzare il file`Write` metodo:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### D: Come posso eseguire la ricerca e la sostituzione del testo utilizzando le espressioni regolari in Aspose.Words per .NET?

 R: Per eseguire la ricerca e la sostituzione del testo utilizzando le espressioni regolari in Aspose.Words per .NET, è possibile utilizzare`Range.Replace` funzione insieme a un modello di espressione regolare. Puoi creare un file`Regex` oggetto con il motivo desiderato e passarlo al file`Replace` metodo:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### D: Come posso utilizzare i gruppi acquisiti nel modello di sostituzione durante la ricerca di testo e sostituirli in Aspose.Words per .NET?

 R: Per utilizzare i gruppi acquisiti nel modello di sostituzione durante la ricerca di testo e la sostituzione in Aspose.Words per .NET, è possibile abilitare il`UseSubstitutions` proprietà del`FindReplaceOptions` oggetto. Ciò consente di fare riferimento ai gruppi acquisiti utilizzando`$1`, `$2`, ecc. nel modello di sostituzione:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### D: Cosa dimostra il codice sorgente di esempio per la funzionalità "Riconoscimento e sostituzioni all'interno dei modelli di sostituzione" in Aspose.Words per .NET?

R: Il codice sorgente di esempio dimostra l'uso della funzionalità "Riconosci e sostituzioni all'interno di modelli di sostituzione" in Aspose.Words per .NET. Mostra come creare un documento, inserire testo, eseguire ricerche e sostituzioni di testo utilizzando espressioni regolari e utilizzare i gruppi acquisiti nel modello di sostituzione per trasformare dinamicamente il testo corrispondente.

#### D: Dove posso trovare ulteriori informazioni ed esempi sull'utilizzo delle espressioni regolari in Aspose.Words per .NET?

R: Per ulteriori informazioni ed esempi sull'utilizzo delle espressioni regolari in Aspose.Words per .NET, è possibile fare riferimento al[Aspose.Words per riferimenti API .NET](https://reference.aspose.com/words/net/). La documentazione fornisce spiegazioni dettagliate ed esempi di codice per vari scenari che coinvolgono espressioni regolari e manipolazione del testo in Aspose.Words per .NET.

#### D: Posso manipolare altri aspetti del documento in base ai gruppi acquisiti durante la ricerca e la sostituzione del testo?

R: Sì, puoi manipolare altri aspetti del documento in base ai gruppi acquisiti durante la ricerca e sostituzione del testo. Oltre a eseguire sostituzioni di testo, puoi modificare la formattazione, gli stili, la struttura del documento e altri elementi in base ai gruppi acquisiti utilizzando le varie API fornite da Aspose.Words per .NET.

#### D: Esistono limitazioni o considerazioni quando si utilizzano espressioni regolari e gruppi acquisiti in Aspose.Words per .NET?

R: Sebbene le espressioni regolari e i gruppi acquisiti offrano potenti funzionalità per la ricerca e la sostituzione del testo in Aspose.Words per .NET, è importante considerare la complessità e le implicazioni sulle prestazioni. Espressioni regolari altamente complesse e un numero elevato di gruppi acquisiti possono influire sulle prestazioni. Si consiglia di testare e ottimizzare le espressioni regolari per i casi d'uso specifici per garantire una manipolazione efficiente dei documenti.

#### D: Posso utilizzare la funzionalità "Riconosci e sostituzioni all'interno dei modelli di sostituzione" con lingue diverse dall'inglese?

R: Sì, la funzionalità "Riconosci e sostituzioni all'interno di modelli di sostituzione" in Aspose.Words per .NET può essere utilizzata con lingue diverse dall'inglese. Le espressioni regolari sono indipendenti dalla lingua e possono essere create per corrispondere a modelli specifici in qualsiasi lingua. Puoi modificare il modello di espressione regolare per adattarlo alla lingua desiderata e ai modelli di testo specifici che desideri riconoscere e sostituire.