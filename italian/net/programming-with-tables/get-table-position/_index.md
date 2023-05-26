---
title: Ottieni posizione al tavolo
linktitle: Ottieni posizione al tavolo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come ottenere la posizione di una tabella in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/get-table-position/
---

In questo tutorial impareremo come ottenere la posizione di una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di ottenere le proprietà di posizionamento della tabella nei tuoi documenti Word a livello di codice.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento e accesso alla tabella
Per iniziare a lavorare con la tabella, dobbiamo caricare il documento che la contiene e accedervi. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Carica il documento
Document doc = new Document(dataDir + "Tables.docx");

// Accesso all'array
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti. Inoltre, assicurati che il documento contenga la tabella di cui vuoi ottenere la posizione.

## Passaggio 3: ottenere le proprietà di posizionamento dell'array
Successivamente, controlleremo il tipo di posizionamento dell'array e otterremo le proprietà di posizionamento appropriate. Usa il seguente codice:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Qui usiamo una condizione per verificare se l'array è di tipo float. In tal caso, stampiamo il file`RelativeHorizontalAlignment` E`RelativeVerticalAlignment` properties per ottenere l'allineamento orizzontale e verticale relativo della tabella. Altrimenti, stampiamo il file`Alignment` property per ottenere l'allineamento dell'array.

### Codice sorgente di esempio per ottenere la posizione della tabella utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Conclusione
In questo tutorial, abbiamo imparato come ottenere la posizione di una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, è possibile ottenere le proprietà di posizionamento della tabella nei documenti di Word a livello di codice. Questa funzione consente di analizzare e manipolare gli array in base alle loro posizioni specifiche.