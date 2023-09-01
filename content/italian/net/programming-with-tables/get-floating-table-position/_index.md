---
title: Ottieni la posizione della tabella mobile
linktitle: Ottieni la posizione della tabella mobile
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come ottenere la posizione delle tabelle mobili in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/get-floating-table-position/
---

In questo tutorial impareremo come ottenere la posizione di una tabella mobile in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzionalità. Alla fine di questo tutorial, sarai in grado di ottenere a livello di codice le proprietà di posizionamento di una tabella mobile nei tuoi documenti Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungi un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento e accesso alle tabelle
Per avviare l'elaborazione parole con le tabelle, dobbiamo caricare il documento che le contiene e accedervi. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti. Inoltre, assicurati che il documento contenga tabelle mobili.

## Passaggio 3: ottenere le proprietà di posizionamento della tabella mobile
Successivamente, scorreremo tutte le tabelle nel documento e otterremo le proprietà di posizionamento della tabella mobile. Utilizza il seguente codice:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Se l'array è di tipo mobile, stampa le sue proprietà di posizionamento.
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

 Qui stiamo usando a`foreach` loop per scorrere tutti gli array nel documento. Controlliamo se l'array è di tipo float controllando il file`TextWrapping` proprietà. In tal caso, stampiamo le proprietà di posizionamento della tabella, come ancoraggio orizzontale, ancoraggio verticale, distanze orizzontali e verticali assolute, autorizzazione di sovrapposizione, distanza orizzontale assoluta e allineamento verticale relativo.
 
### Codice sorgente di esempio per Ottieni posizione tabella mobile utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Se la tabella è di tipo mobile, stampa le sue proprietà di posizionamento.
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
In questo tutorial, abbiamo imparato come ottenere la posizione di una tabella mobile in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, è possibile ottenere a livello di codice le proprietà di posizionamento delle tabelle mobili nei documenti di Word. Questa funzionalità ti consente di analizzare e manipolare le tabelle mobili in base alle tue esigenze specifiche.