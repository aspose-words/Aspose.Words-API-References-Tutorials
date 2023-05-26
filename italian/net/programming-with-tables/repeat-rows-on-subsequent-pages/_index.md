---
title: Ripeti le righe nelle pagine successive
linktitle: Ripeti le righe nelle pagine successive
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come ripetere le righe della tabella nelle pagine successive in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

In questo tutorial impareremo come ripetere le righe di una tabella nelle pagine successive di un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di specificare le righe da ripetere nelle pagine successive della tua tabella nei tuoi documenti Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento e inizializzazione del generatore di documenti
Per iniziare a lavorare con il documento e il generatore di documenti, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti
Document doc = new Document();

// Inizializza il generatore di documenti
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 3: costruire la tabella con righe ripetute
Successivamente, costruiremo una tabella con righe ripetute nelle pagine successive. Usa il seguente codice:

```csharp
// Inizio del tavolo
builder. StartTable();

// Configurazione dei parametri di prima riga (righe di intestazione)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Inserisci la prima cella della prima riga
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Inserisci la seconda cella della prima riga
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Configurare i parametri delle seguenti righe
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Loop per inserire le celle nelle righe successive
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Fine del tavolo
builder. EndTable();
```

 Qui usiamo il generatore di documenti per creare una tabella con due righe di intestazione e più righe di dati. IL`RowFormat.HeadingFormat` parametri vengono utilizzati per contrassegnare le righe di intestazione che devono essere ripetute nelle pagine successive.

## Passaggio 4: salvare il documento modificato
Infine NOI

  necessità di salvare il documento modificato con le righe di intestazione ripetute nelle pagine successive della tabella. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Esempio di codice sorgente per Ripeti righe nelle pagine successive utilizzando Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato a ripetere le righe di una tabella nelle pagine successive di un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida passo-passo e implementando il codice C# fornito, puoi specificare quali righe ripetere in base alle tue esigenze specifiche nei tuoi documenti Word.