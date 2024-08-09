---
title: Formato riga Disabilita interruzione tra le pagine
linktitle: Formato riga Disabilita interruzione tra le pagine
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come disabilitare le interruzioni di riga tra le pagine nei documenti di Word utilizzando Aspose.Words per .NET per mantenere la leggibilità e la formattazione della tabella.
type: docs
weight: 10
url: /it/net/programming-with-tables/row-format-disable-break-across-pages/
---
## Introduzione

Quando lavori con le tabelle nei documenti di Word, potresti voler assicurarti che le righe non si dividano tra le pagine, il che può essere essenziale per mantenere la leggibilità e la formattazione dei tuoi documenti. Aspose.Words per .NET fornisce un modo semplice per disabilitare le interruzioni di riga tra le pagine.

In questo tutorial, ti guideremo attraverso il processo di disabilitazione delle interruzioni di riga tra le pagine in un documento Word utilizzando Aspose.Words per .NET.

## Prerequisiti

Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata.
- Un documento Word con una tabella che si estende su più pagine.

## Importa spazi dei nomi

Innanzitutto, importa gli spazi dei nomi necessari nel tuo progetto:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Passaggio 1: caricare il documento

Caricare il documento contenente la tabella che si estende su più pagine.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Passaggio 2: accedi alla tabella

Accedi alla prima tabella del documento. Ciò presuppone che la tabella che desideri modificare sia la prima tabella nel documento.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Passaggio 3: disabilita l'interruzione delle pagine per tutte le righe

 Passa in rassegna ogni riga della tabella e imposta il file`AllowBreakAcrossPages`proprietà a`false`. Ciò garantisce che le righe non si spezzino tra le pagine.

```csharp
// Disabilita la suddivisione delle pagine per tutte le righe della tabella.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## Passaggio 4: salva il documento

Salva il documento modificato nella directory specificata.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusione

In questo tutorial, abbiamo dimostrato come disabilitare le interruzioni di riga tra le pagine in un documento Word utilizzando Aspose.Words per .NET. Seguendo i passaggi sopra descritti, puoi assicurarti che le righe della tabella rimangano intatte e non siano divise su pagine, mantenendo la leggibilità e la formattazione del documento.

## Domande frequenti

### Posso disabilitare le interruzioni di riga tra le pagine per una riga specifica anziché per tutte le righe?  
 Sì, puoi disabilitare le interruzioni di riga per righe specifiche accedendo alla riga desiderata e impostandola`AllowBreakAcrossPages`proprietà a`false`.

### Questo metodo funziona per tabelle con celle unite?  
 Sì, questo metodo funziona per tabelle con celle unite. La proprietà`AllowBreakAcrossPages` si applica all'intera riga, indipendentemente dall'unione delle celle.

### Questo metodo funzionerà se la tabella è nidificata all'interno di un'altra tabella?  
Sì, puoi accedere e modificare le tabelle nidificate allo stesso modo. Assicurati di fare riferimento correttamente alla tabella nidificata tramite il suo indice o altre proprietà.

### Come posso verificare se una riga consente la suddivisione tra le pagine?  
 Puoi verificare se una riga consente la suddivisione tra le pagine accedendo al file`AllowBreakAcrossPages` proprietà del`RowFormat` e verificandone il valore.

### C'è un modo per applicare questa impostazione a tutte le tabelle in un documento?  
Sì, puoi scorrere tutte le tabelle del documento e applicare questa impostazione a ciascuna di esse.