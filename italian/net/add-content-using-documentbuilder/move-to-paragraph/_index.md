---
title: Sposta al paragrafo
linktitle: Sposta al paragrafo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare Aspose.Words per la funzione Sposta in paragrafo di .NET per navigare e manipolare i paragrafi nei documenti di Word a livello di codice.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/move-to-paragraph/
---

In questo esempio dettagliato, esploreremo la funzionalità Sposta in paragrafo di Aspose.Words per .NET. Questa funzionalità consente agli sviluppatori di navigare e manipolare i paragrafi all'interno di un documento di Word a livello di codice. Seguendo questa guida, imparerai come implementare e utilizzare la funzione Sposta in paragrafo in modo efficace.

Il codice precedente illustra l'utilizzo della funzione Sposta in paragrafo. Comprendiamo ogni passaggio in dettaglio:

## Passaggio 1: caricamento del documento

 Iniziamo caricando il documento di Word in un'istanza del file`Document` classe. IL`MyDir`La variabile rappresenta il percorso della directory in cui si trova il documento. Dovresti sostituirlo con il percorso effettivo della directory o modificare il codice di conseguenza.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
```

## Passaggio 2: inizializzazione di DocumentBuilder

 Successivamente, creiamo un file`DocumentBuilder` oggetto e associarlo al documento caricato. IL`DocumentBuilder` class fornisce vari metodi e proprietà per manipolare il contenuto del documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: passaggio a un paragrafo specifico

 IL`MoveToParagraph` metodo viene utilizzato per posizionare il generatore di documenti in un paragrafo specifico all'interno del documento. Prende due parametri: l'indice del paragrafo di destinazione e la posizione del carattere all'interno di quel paragrafo (0 rappresenta l'inizio del paragrafo).

Nell'esempio fornito, passiamo al terzo paragrafo (indice 2) del documento:

```csharp
builder.MoveToParagraph(2, 0);
```

## Passaggio 4: modifica del contenuto del paragrafo

 Una volta posizionato il builder nel paragrafo desiderato, possiamo utilizzare il`Writeln`metodo per aggiungere o modificare il contenuto di quel paragrafo. In questo caso, aggiungiamo il testo "Questo è il terzo paragrafo".

```csharp
builder.Writeln("This is the 3rd paragraph.");
```

### Esempio di codice sorgente per Sposta al paragrafo utilizzando Aspose.Words per .NET

Di seguito è riportato il codice sorgente di esempio completo per l'implementazione della funzione Sposta in paragrafo utilizzando Aspose.Words per .NET:

```csharp

	Document doc = new Document(MyDir + "Paragraphs.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.MoveToParagraph(2, 0);
	builder.Writeln("This is the 3rd paragraph.");
	
```

Seguendo questa guida e utilizzando la funzione Sposta in paragrafo, puoi manipolare a livello di codice i paragrafi all'interno dei documenti di Word utilizzando Aspose.Words per .NET.

