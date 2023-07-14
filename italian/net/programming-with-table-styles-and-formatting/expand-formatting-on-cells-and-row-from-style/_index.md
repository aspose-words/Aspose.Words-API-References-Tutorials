---
title: Espandi la formattazione su celle e riga dallo stile
linktitle: Espandi la formattazione su celle e riga dallo stile
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata per espandere la formattazione a celle e righe da uno stile di tabella utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

In questo tutorial, ti guideremo attraverso il processo dettagliato per espandere la formattazione a celle e righe da uno stile utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come applicare la formattazione in stile tabella a celle e righe specifiche nei tuoi documenti Word utilizzando Aspose.Words per .NET.


## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Qui è dove si trova il tuo documento Word. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: carica il documento esistente
 Successivamente, è necessario caricare il documento Word esistente in un'istanza del file`Document` classe.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Passaggio 3: vai alla prima cella della prima tabella
 Per iniziare, dobbiamo navigare fino alla prima cella della prima tabella nel documento. Noi usiamo il`GetChild()` E`FirstRow.FirstCell` metodi per ottenere il riferimento alla prima cella.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Passaggio 4: mostra la formattazione iniziale della cella
Prima di espandere gli stili della tabella, visualizziamo il colore di sfondo corrente della cella. Questo dovrebbe essere vuoto perché la formattazione corrente è memorizzata nello stile della tabella.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Passaggio 5: espandere gli stili di tabella alla formattazione diretta
 Ora espandiamo gli stili di tabella per indirizzare la formattazione utilizzando quelli del documento`ExpandTableStylesToDirectFormatting()` metodo.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Passaggio 6: mostra la formattazione della cella dopo l'espansione dello stile
Ora visualizziamo il colore di sfondo della cella dopo aver espanso gli stili di tabella. Un colore di sfondo blu dovrebbe essere applicato dallo stile della tabella.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Esempio di codice sorgente per espandere la formattazione su celle e riga dallo stile utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Ottieni la prima cella della prima tabella nel documento.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Per prima cosa stampa il colore dell'ombreggiatura della cella.
	// Questo dovrebbe essere vuoto poiché l'ombreggiatura corrente è memorizzata nello stile della tabella.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Ora stampa l'ombreggiatura della cella dopo aver espanso gli stili di tabella.
	// Dovrebbe essere stato applicato un colore del motivo di sfondo blu dallo stile della tabella.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Conclusione
In questo tutorial, abbiamo imparato come espandere la formattazione a celle e righe da uno stile di tabella utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata, puoi facilmente applicare la formattazione dello stile tabella a celle e righe specifiche nei tuoi documenti Word. Aspose.Words offre un'API potente e flessibile per la manipolazione e la formattazione delle tabelle nei tuoi documenti. Con questa conoscenza, puoi personalizzare ulteriormente il layout e la presentazione dei tuoi documenti Word.