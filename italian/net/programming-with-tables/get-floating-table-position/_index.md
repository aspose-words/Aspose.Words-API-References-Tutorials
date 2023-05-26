---
title: Ottieni la posizione del tavolo mobile
linktitle: Ottieni la posizione del tavolo mobile
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come ottenere la posizione delle tabelle mobili in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/get-floating-table-position/
---

In questo tutorial impareremo come ottenere la posizione di una tabella mobile in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di ottenere le proprietà di posizionamento di una tabella mobile nei tuoi documenti Word a livello di codice.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento e accesso alle tabelle
Per iniziare a lavorare con le tabelle, dobbiamo caricare il documento che le contiene e accedervi. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Carica il documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti. Inoltre, assicurati che il documento contenga tabelle mobili.

## Passaggio 3: ottenere le proprietà di posizionamento della tabella mobile
Successivamente, eseguiremo il ciclo di tutte le tabelle nel documento e otterremo le proprietà di posizionamento della tabella mobile. Usa il seguente codice:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Se l'array è di tipo mobile, stampane le proprietà di posizionamento.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Qui stiamo usando un`foreach` loop per scorrere tutti gli array nel documento. Controlliamo se l'array è di tipo float controllando il file`TextWrapping` proprietà. Se è così, stampiamo le proprietà di posizionamento della tabella, come l'ancora orizzontale, l'ancora verticale, le distanze assolute orizzontali e verticali, il permesso di sovrapposizione, la distanza orizzontale assoluta e l'allineamento verticale relativo.
 
### Codice sorgente di esempio per ottenere la posizione della tabella mobile utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Se la tabella è di tipo mobile, stampane le proprietà di posizionamento.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Conclusione
In questo tutorial, abbiamo imparato come ottenere la posizione di una tabella mobile in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, è possibile ottenere le proprietà di posizionamento delle tabelle mobili nei documenti di Word a livello di codice. Questa funzione consente di analizzare e manipolare le tabelle mobili in base alle proprie esigenze specifiche.