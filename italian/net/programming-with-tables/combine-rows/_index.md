---
title: Combina righe
linktitle: Combina righe
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come combinare le righe della tabella in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/combine-rows/
---

In questo tutorial impareremo come utilizzare Aspose.Words per .NET per combinare righe di tabelle in un documento Word. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di manipolare e unire le righe della tabella nei tuoi documenti Word in modo programmatico.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento e accesso alle tabelle
Per iniziare a lavorare con le tabelle, dobbiamo caricare il documento che le contiene e accedervi. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Carica il documento
Document doc = new Document(dataDir + "Tables.docx");

// Accesso ai tavoli
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 3: combinazione delle righe della tabella
Successivamente, combineremo le righe della seconda tabella alla fine della prima tabella. Usa il seguente codice:

```csharp
// Combinazione di righe della tabella
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Qui usiamo a`while` loop per iterare su tutte le righe del secondo array e aggiungerle alla fine del primo array usando il`Add` metodo. Successivamente, rimuoviamo la seconda tabella dal documento utilizzando l'estensione`Remove` metodo.

## Passaggio 4: salvare il documento modificato
Infine, dobbiamo salvare il documento modificato con le righe della tabella combinate. Usa il seguente codice:

```csharp
// Salva il documento modificato
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Esempio di codice sorgente per Combina righe utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Le righe della seconda tabella verranno aggiunte alla fine della prima tabella.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Accoda tutte le righe dalla tabella corrente alle tabelle successive
	// con numero di celle e larghezze diverse possono essere uniti in un'unica tabella.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come combinare righe di tabelle in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, puoi manipolare le righe della tabella nei documenti di Word a livello di programmazione. Questa funzione ti consente di unire e organizzare in modo efficiente i tuoi dati in una tabella.