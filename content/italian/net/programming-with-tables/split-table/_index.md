---
title: Tabella divisa
linktitle: Tabella divisa
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come dividere una tabella in un documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/split-table/
---

In questo tutorial impareremo come dividere una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzionalità. Alla fine di questo tutorial sarai in grado di dividere una tabella da una determinata riga nei tuoi documenti Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungi un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento
Per avviare l'elaborazione parole con il documento, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento
Document doc = new Document(dataDir + "Tables.docx");
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti e fornisci il nome file corretto.

## Passaggio 3: divisione della tabella
Successivamente divideremo la tabella da una determinata riga. Utilizza il seguente codice:

```csharp
// Recupera la prima tabella
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Determinazione della linea da cui dividere la tabella
Row row = firstTable.Rows[2];

// Crea un nuovo contenitore per la tabella divisa
Table table = (Table)firstTable.Clone(false);

// Inserire il contenitore dopo la tabella originale
firstTable.ParentNode.InsertAfter(table, firstTable);

// Aggiungi un paragrafo buffer per mantenere una distanza tra le tabelle
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Sposta le righe dalla tabella originale alla tabella divisa
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Qui utilizziamo il documento per recuperare la prima tabella dal nodo del documento. Successivamente determiniamo la riga da cui vogliamo dividere la tabella, in questo esempio è la terza riga (indice 2). Creiamo quindi un nuovo contenitore clonando la tabella originale e quindi inserendolo dopo la tabella originale. Aggiungiamo anche un paragrafo buffer per mantenere una distanza tra le due tabelle. Quindi spostiamo le righe dalla tabella originale alla tabella divisa utilizzando un ciclo do- while finché non raggiungiamo la riga specificata.

## Passaggio 4: salvataggio del documento modificato
Infine, dobbiamo salvare il file

  documento modificato con la tabella divisa. Utilizza il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per Split Table utilizzando Aspose.Words per .NET 

```csharp
//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Divideremo la tabella nella terza riga (inclusa).
Row row = firstTable.Rows[2];
// Crea un nuovo contenitore per la tabella divisa.
Table table = (Table) firstTable.Clone(false);
// Inserire il contenitore dopo l'originale.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Aggiungi un paragrafo buffer per garantire che le tabelle rimangano separate.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come dividere una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo e implementando il codice C# fornito, puoi facilmente dividere le tabelle da una determinata riga nei tuoi documenti Word.