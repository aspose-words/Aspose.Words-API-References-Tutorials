---
title: Formato riga Disabilita interruzione tra le pagine
linktitle: Formato riga Disabilita interruzione tra le pagine
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come disabilitare l'interruzione di riga per una tabella su più pagine in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/row-format-disable-break-across-pages/
---

In questo tutorial impareremo come disabilitare l'interruzione di riga di una tabella multipagina in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzionalità. Entro la fine di questo tutorial, sarai in grado di disabilitare l'interruzione di riga per tutte le righe nella tabella nei tuoi documenti Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungi un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento
Per avviare l'elaborazione parole con il documento, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti e fornisci il nome file corretto.

## Passaggio 3: disabilita l'interruzione di riga della tabella
Successivamente, disabiliteremo l'interruzione di riga per tutte le righe nella tabella. Utilizza il seguente codice:

```csharp
// Recupera la tabella
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Disabilita l'interruzione di riga per tutte le righe nella tabella
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Qui utilizziamo il documento per recuperare la prima tabella e quindi scorrere tutte le righe della tabella utilizzando un ciclo foreach. All'interno del ciclo, disabilitiamo l'interruzione di riga per ogni riga impostando il file`RowFormat.AllowBreakAcrossPages`proprietà a`false`.

## Passaggio 4: salvataggio del documento modificato
Infine, dobbiamo salvare il documento modificato con l'interruzione di riga della tabella disabilitata. Utilizza il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per il formato riga Disabilita interruzione tra le pagine utilizzando Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Disabilita la suddivisione delle pagine per tutte le righe della tabella.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come disabilitare l'interruzione di riga di una tabella multipagina in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo e implementando il codice C# fornito, puoi applicare questa disabilitazione alle tabelle nei tuoi documenti Word.