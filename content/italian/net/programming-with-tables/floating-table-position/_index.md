---
title: Posizione del tavolo mobile
linktitle: Posizione del tavolo mobile
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come posizionare una tabella in una posizione mobile in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/floating-table-position/
---

In questo tutorial impareremo come utilizzare Aspose.Words per .NET per posizionare una tabella in una posizione mobile in un documento Word. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzionalità. Alla fine di questo tutorial, sarai in grado di controllare a livello di codice la posizione e l'allineamento delle tabelle mobili nei tuoi documenti Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungi un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento e accesso alla tabella
Per avviare l'elaborazione testi con la tabella, dobbiamo caricare il documento che la contiene e accedervi. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Accesso all'array
Table table = doc.FirstSection.Body.Tables[0];
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti. Inoltre, assicurati che il documento contenga una tabella che verrà posizionata in una posizione mobile.

## Passaggio 3: posizionamento della tavola mobile
Successivamente, posizioneremo la tabella in una posizione mobile utilizzando le proprietà fornite da Aspose.Words per .NET. Utilizza il seguente codice:

```csharp
// Posizionamento del tavolo mobile
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Qui usiamo il`AbsoluteHorizontalDistance` proprietà per impostare la distanza orizzontale assoluta della tabella dal bordo sinistro della pagina. Usiamo anche il`RelativeVerticalAlignment` proprietà per impostare l'allineamento verticale relativo della tabella rispetto al contenuto circostante.

## Passaggio 4: salvataggio del documento modificato
Infine, dobbiamo salvare il documento modificato con la tabella posizionata in posizione mobile. Utilizza il seguente codice:

```csharp
// Salva il documento modificato
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per la posizione della tabella mobile utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come posizionare una tabella in una posizione mobile in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo e implementando il codice C# fornito, puoi controllare la posizione e l'allineamento delle tabelle mobili nei tuoi documenti Word a livello di codice.