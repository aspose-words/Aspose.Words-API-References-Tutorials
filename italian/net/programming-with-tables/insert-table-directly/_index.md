---
title: Inserisci tabella direttamente
linktitle: Inserisci tabella direttamente
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire una tabella direttamente in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/insert-table-directly/
---

In questo tutorial impareremo come inserire direttamente una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di inserire tabelle direttamente nei tuoi documenti Word a livello di programmazione.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento e della tabella
Per iniziare a lavorare con l'array, dobbiamo creare un nuovo documento e inizializzare l'array. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti
Document doc = new Document();

// Crea la matrice
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 3: creazione dell'array
Successivamente, costruiremo la tabella aggiungendo righe e celle. Utilizzare il seguente codice come esempio:

```csharp
// Crea la prima riga
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Crea la prima cella
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Duplica la cella per la seconda cella nella riga
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Qui creiamo una riga con il`AllowBreakAcrossPages` proprietà impostata su`true` per consentire l'interruzione di pagina tra le righe. Quindi creiamo una cella con uno sfondo colorato, larghezza fissa e contenuto di testo specificato. Quindi duplichiamo questa cella per creare la seconda cella nella riga.

## Passaggio 4: tabella di adattamento automatico
Possiamo applicare regolazioni automatiche alla tabella per formattarla correttamente. Usa il seguente codice:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Questa riga di codice applica un adattamento automatico basato su larghezze di colonna fisse.

## Passaggio 5: registrazione del file

  documento modificato
Infine, dobbiamo salvare il documento modificato con la tabella inserita direttamente. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Esempio di codice sorgente per Inserisci tabella direttamente utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Iniziamo creando l'oggetto tabella. Si noti che dobbiamo passare l'oggetto documento
	//al costruttore di ciascun nodo. Questo perché ogni nodo che creiamo deve appartenere
	// a qualche documento.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Qui potremmo chiamare GuaranteeMinimum per creare le righe e le celle per noi. Questo metodo è usato
	// per garantire che il nodo specificato sia valido. In questo caso, una tabella valida dovrebbe avere almeno una riga e una cella.
	// Invece, ci occuperemo noi stessi della creazione della riga e della tabella.
	// Questo sarebbe il modo migliore per farlo se stessimo creando una tabella all'interno di un algoritmo.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Ora possiamo applicare qualsiasi impostazione di adattamento automatico.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Dovremmo quindi ripetere il processo per le altre celle e righe nella tabella.
	// Possiamo anche accelerare le cose clonando celle e righe esistenti.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come inserire direttamente una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, è possibile inserire tabelle direttamente nei documenti di Word a livello di codice. Questa funzionalità consente di creare e personalizzare le tabelle in base alle proprie esigenze specifiche.