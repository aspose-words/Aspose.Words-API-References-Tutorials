---
title: Converti in celle unite orizzontalmente
linktitle: Converti in celle unite orizzontalmente
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come convertire le celle della tabella in celle unite orizzontalmente in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

In questo tutorial impareremo come utilizzare Aspose.Words per .NET per convertire le celle della tabella in celle unite orizzontalmente in un documento di Word. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di manipolare le celle della tabella nei tuoi documenti Word a livello di codice.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento e accesso alla tabella
Per iniziare a lavorare con la tabella, dobbiamo caricare il documento che la contiene e accedervi. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Carica il documento
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Accesso all'array
Table table = doc.FirstSection.Body.Tables[0];
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti. Inoltre, assicurati che il documento contenga una tabella con celle unite orizzontalmente.

## Passaggio 3: converti in celle unite orizzontalmente
 Successivamente, convertiremo le celle della tabella in celle unite orizzontalmente utilizzando il file`ConvertToHorizontallyMergedCells()` metodo. Usa il seguente codice:

```csharp
// Converti in celle unite orizzontalmente
table. ConvertToHorizontallyMergedCells();
```

 Qui chiamiamo semplicemente il`ConvertToHorizontallyMergedCells()` metodo sull'array per eseguire la conversione.

### Esempio di codice sorgente per Converti in celle unite orizzontalmente utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Ora le celle unite hanno flag di unione appropriati.
	table.ConvertToHorizontallyMergedCells();
```

## Conclusione
In questo tutorial, abbiamo imparato come convertire le celle della tabella in celle unite orizzontalmente in un documento di Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, puoi manipolare le celle della tabella nei documenti di Word a livello di programmazione. Questa funzionalità ti consente di gestire e organizzare i tuoi dati in modo flessibile e personalizzato in una tabella.