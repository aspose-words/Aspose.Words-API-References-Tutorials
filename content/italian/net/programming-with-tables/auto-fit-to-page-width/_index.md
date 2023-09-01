---
title: Adattamento automatico alla larghezza della pagina
linktitle: Adattamento automatico alla larghezza della pagina
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come adattare automaticamente una tabella alla larghezza della pagina in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/auto-fit-to-page-width/
---

In questo tutorial impareremo come utilizzare Aspose.Words per .NET per adattare automaticamente una tabella alla larghezza della pagina in un documento Word. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzionalità. Alla fine di questo tutorial sarai in grado di manipolare le tabelle nei documenti Word a livello di codice.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungi un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione e configurazione del documento
Per avviare l'elaborazione parole con la tabella, dobbiamo creare un documento e configurare il generatore di documenti. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e il generatore di documenti
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti.

## Passaggio 3: inserimento e configurazione della tabella
Successivamente, inseriremo una tabella nel documento con una larghezza che occupi metà della larghezza della pagina. Utilizza il seguente codice:

```csharp
// Inserisci la tabella e configurane la larghezza
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Qui utilizziamo il generatore di documenti per iniziare a creare la tabella, inserire celle e impostare la larghezza preferita della tabella al 50% della larghezza della pagina. Quindi aggiungiamo il testo in ogni cella.

## Passaggio 4: salvataggio del documento modificato
Infine, dobbiamo salvare il documento modificato con la tabella adattata alla larghezza della pagina. Utilizza il seguente codice:

```csharp
// Salva il documento modificato
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.
  
### Codice sorgente di esempio per l'adattamento automatico alla larghezza della pagina utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Inserisci una tabella con una larghezza che occupi metà della larghezza della pagina.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come adattare automaticamente una tabella alla larghezza della pagina in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo e implementando il codice C# fornito, puoi manipolare le tabelle nei tuoi documenti Word a livello di codice. Questa funzionalità consente di adattare dinamicamente la larghezza della tabella in base alla pagina, offrendo così un documento professionale e visivamente accattivante.