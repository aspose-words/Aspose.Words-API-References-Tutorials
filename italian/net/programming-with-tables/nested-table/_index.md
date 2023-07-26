---
title: Tabella nidificata
linktitle: Tabella nidificata
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come creare una tabella nidificata in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/nested-table/
---

In questo tutorial impareremo come creare una tabella nidificata in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di creare tabelle nidificate nei tuoi documenti Word a livello di codice.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento e inizializzazione del generatore di documenti
Per avviare l'elaborazione di testi con il documento e il generatore di documenti, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti
Document doc = new Document();

// Inizializza il generatore di documenti
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 3: creazione della tabella nidificata
Successivamente, costruiremo la tabella nidificata inserendo celle nella tabella esterna e creando una nuova tabella all'interno della prima cella. Usa il seguente codice:

```csharp
// Inserisci la prima cella della tabella esterna
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Inserisci la seconda cella della tabella esterna
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Terminazione della tabella esterna
builder. EndTable();

// Passa alla prima cella della tabella esterna
builder.MoveTo(cell.FirstParagraph);

// Costruisci il tavolo interno
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Fine del tavolo interno
builder. EndTable();
```

Qui usiamo il generatore di documenti per inserire celle e contenuto nella tabella esterna. Quindi spostiamo il cursore del generatore di documenti sulla prima cella della tabella esterna e creiamo una nuova tabella all'interno inserendo celle e contenuto.

## Passaggio 4: salvare il documento modificato
Infine, dobbiamo salvare il documento modificato con la tabella nidificata. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Assicurarsi di specificare il percorso e il nome file corretti per il documento di output.

### Esempio di codice sorgente per Nested Table utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Questa chiamata è importante per creare una tabella nidificata all'interno della prima tabella.
	// Senza questa chiamata, le celle inserite di seguito verranno aggiunte alla tabella esterna.
	builder.EndTable();
	// Passa alla prima cella della tabella esterna.
	builder.MoveTo(cell.FirstParagraph);
	// Costruisci il tavolo interno.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come creare una tabella nidificata in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, puoi creare tabelle nidificate in base alle tue esigenze specifiche nei tuoi documenti Word a livello di programmazione.
