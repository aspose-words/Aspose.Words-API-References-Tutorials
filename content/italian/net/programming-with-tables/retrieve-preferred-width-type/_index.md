---
title: Recupera il tipo di larghezza preferito
linktitle: Recupera il tipo di larghezza preferito
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come recuperare il tipo e il valore di larghezza preferito di una cella in una tabella di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/retrieve-preferred-width-type/
---

In questo tutorial impareremo come recuperare il tipo di larghezza preferito e il suo valore da una cella di tabella in un documento di Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di recuperare il tipo di larghezza preferito (assoluto, relativo o automatico) e il suo valore per una cella specifica nelle tabelle del tuo documento Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento
Per avviare l'elaborazione di parole con il documento, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento
Document doc = new Document(dataDir + "Tables.docx");
```

Assicurati di sostituire "YOUR DOCUMENTS DIRECTORY" con il percorso effettivo della directory dei documenti e fornisci il nome file corretto.

## Passaggio 3: recupero del tipo e del valore di larghezza preferiti
Successivamente, recupereremo il tipo di larghezza preferito e il relativo valore per una specifica cella della tabella. Usa il seguente codice:

```csharp
// Recupera il tavolo
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Attiva la regolazione automatica del tavolo
table. AllowAutoFit = true;

// Recupera la prima cella della prima riga
Cell firstCell = table.FirstRow.FirstCell;

// Recupera il tipo di larghezza preferito e il relativo valore
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

Qui usiamo il documento per recuperare la prima tabella, quindi abilitiamo l'adattamento automatico della tabella con il`AllowAutoFit` proprietà. Quindi recuperiamo la prima cella della prima riga della tabella. Da questa cella, possiamo recuperare il tipo di larghezza preferito con il`PreferredWidth.Type` proprietà e il suo valore con il`PreferredWidth.Value` proprietà.

### Esempio di codice sorgente per il recupero del tipo di larghezza preferito utilizzando Aspose.Words per .NET 

```csharp
//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Conclusione
In questo tutorial, abbiamo imparato come recuperare il tipo di larghezza preferito e il suo valore da una cella di tabella in un documento di Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, puoi recuperare queste informazioni per celle specifiche nelle tabelle del documento di Word.