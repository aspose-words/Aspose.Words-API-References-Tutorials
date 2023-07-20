---
title: Formato riga Disabilita l'interruzione tra le pagine
linktitle: Formato riga Disabilita l'interruzione tra le pagine
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come disabilitare l'interruzione di riga per una tabella su più pagine in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/row-format-disable-break-across-pages/
---

In questo tutorial impareremo come disabilitare l'interruzione di riga di una tabella a più pagine in un documento di Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di disabilitare l'interruzione di riga per tutte le righe della tabella nei documenti di Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento
Per avviare l'elaborazione di parole con il documento, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Assicurati di sostituire "YOUR DOCUMENTS DIRECTORY" con il percorso effettivo della directory dei documenti e fornisci il nome file corretto.

## Passaggio 3: disabilitare l'interruzione di riga della tabella
Successivamente, disabiliteremo l'interruzione di riga per tutte le righe nella tabella. Usa il seguente codice:

```csharp
// Recupera il tavolo
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Disabilita l'interruzione di riga per tutte le righe della tabella
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Qui usiamo il documento per recuperare la prima tabella e poi iteriamo attraverso tutte le righe della tabella usando un ciclo foreach. All'interno del ciclo, disabilitiamo l'interruzione di riga per ogni riga impostando il`RowFormat.AllowBreakAcrossPages` proprietà a`false`.

## Passaggio 4: salvare il documento modificato
Infine, dobbiamo salvare il documento modificato con l'interruzione di riga della tabella disabilitata. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per il formato di riga Disabilita l'interruzione tra le pagine utilizzando Aspose.Words per .NET 

```csharp
//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Disabilita l'interruzione tra le pagine per tutte le righe della tabella.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come disabilitare l'interruzione di riga di una tabella multipagina in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, puoi applicare questa disabilitazione alle tue tabelle nei tuoi documenti Word.