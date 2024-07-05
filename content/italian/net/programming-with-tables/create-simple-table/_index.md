---
title: Crea tabella semplice
linktitle: Crea tabella semplice
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come creare una tabella semplice in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/create-simple-table/
---

In questo tutorial impareremo come creare una semplice tabella in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzionalità. Alla fine di questo tutorial, sarai in grado di creare tabelle personalizzate nei tuoi documenti Word a livello di codice.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungi un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento e inizializzazione del generatore di documenti
Per iniziare a costruire la tabella, dobbiamo creare un nuovo documento e inizializzare il generatore di documenti. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e inizializzare il generatore di documenti
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti.

## Passaggio 3: creazione dell'array
Successivamente, costruiremo la tabella utilizzando i metodi forniti dal generatore di documenti. Utilizza il seguente codice:

```csharp
// Inizia la costruzione dell'array
builder. StartTable();

// Costruzione della prima cella della prima riga
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Costruzione della seconda cella della prima fila
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//Chiama il metodo seguente per terminare la prima riga e iniziare una nuova riga
builder. EndRow();

// Costruzione della prima cella della seconda fila
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Costruzione della seconda cella della seconda fila
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Chiama il metodo successivo per terminare la seconda riga
builder. EndRow();

// Indicazione che la costruzione del tavolo è terminata
builder. EndTable();
```

 Qui utilizziamo il generatore di documenti per costruire la tabella passo dopo passo. Iniziamo chiamando`StartTable()` per inizializzare la tabella, quindi utilizzare`InsertCell()` per inserire celle e`Write()` per aggiungere contenuto a ciascuna cella. Usiamo anche`EndRow()` per terminare una riga e iniziare una nuova riga. Infine chiamiamo`EndTable()` per indicare che la costruzione della tabella è completa.

## Passaggio 4: salva il documento
Infine, dobbiamo risparmiare

  il documento con la tabella creata. Utilizza il seguente codice:

```csharp
// Salva il documento
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per Crea tabella semplice utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Inizia a costruire la tabella.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Costruisci la seconda cella.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Chiama il metodo seguente per terminare la riga e iniziare una nuova riga.
	builder.EndRow();
	// Costruisci la prima cella della seconda riga.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Costruisci la seconda cella.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//Segnala che abbiamo finito di costruire la tabella.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come creare una semplice tabella in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo e implementando il codice C# fornito, puoi creare tabelle personalizzate nei tuoi documenti Word a livello di codice. Questa funzionalità ti consente di formattare e organizzare i tuoi dati in modo strutturato e chiaro.