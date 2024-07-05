---
title: Applica bordo contorno
linktitle: Applica bordo contorno
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per applicare un bordo di contorno a una tabella utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

In questo tutorial ti guideremo attraverso il processo passo passo per applicare un bordo di contorno a una tabella utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, avrai una chiara comprensione di come manipolare i bordi delle tabelle nei tuoi documenti Word utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Qui è dove è archiviato il tuo documento Word. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: carica il documento
 Successivamente, è necessario caricare il documento Word in un'istanza del file`Document` classe.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Passaggio 3: accedi alla tabella
 Per applicare un bordo di contorno, dobbiamo accedere alla tabella nel documento. IL`Table` la classe rappresenta una tabella in Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Passaggio 4: allinea la tabella al centro della pagina
 Ora possiamo allineare la tabella al centro della pagina utilizzando il`Alignment` proprietà della tabella.

```csharp
table. Alignment = Table Alignment. Center;
```

## Passaggio 5: cancella i bordi della tabella esistente
Per iniziare con un nuovo bordo del contorno, dobbiamo prima cancellare tutti i bordi esistenti dalla tabella. Questo può essere fatto utilizzando il`ClearBorders()` metodo.

```csharp
table. ClearBorders();
```

## Passaggio 6: Definire un bordo verde attorno al tavolo
 Ora possiamo impostare un bordo verde attorno al tavolo usando il`SetBorder()` metodo per ciascun lato del tavolo. In questo esempio utilizziamo un bordo di tipo "Singolo" con uno spessore di 1,5 punti e un colore verde.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Passaggio 7: riempi le celle con un colore di sfondo
Per migliorare la presentazione visiva della tabella, possiamo riempire le celle con un colore di sfondo terra

idea. In questo esempio, stiamo usando un colore verde chiaro.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Passaggio 8: salva il documento modificato
Infine, salviamo il documento modificato in un file. È possibile scegliere un nome e una posizione appropriati per il documento di output.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Congratulazioni! Ora hai applicato un bordo di contorno a una tabella utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Applicare il bordo del contorno utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Allinea la tabella al centro della pagina.
	table.Alignment = TableAlignment.Center;
	//Cancella eventuali bordi esistenti dalla tabella.
	table.ClearBorders();
	// Imposta un bordo verde attorno al tavolo ma non all'interno.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Riempi le celle con un colore solido verde chiaro.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come applicare un bordo di contorno a una tabella utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo, puoi integrare facilmente questa funzionalità nei tuoi progetti C#. La manipolazione della formattazione della tabella è un aspetto essenziale dell'elaborazione dei documenti e Aspose.Words offre un'API potente e flessibile per raggiungere questo obiettivo. Con questa conoscenza, puoi migliorare la presentazione visiva dei tuoi documenti Word e soddisfare requisiti specifici.