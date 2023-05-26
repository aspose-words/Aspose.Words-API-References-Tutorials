---
title: Esporta in markdown con allineamento del contenuto della tabella
linktitle: Esporta in markdown con allineamento del contenuto della tabella
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come esportare il contenuto della tabella con diversi allineamenti in file Markdown utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Ecco una guida dettagliata per spiegare il seguente codice sorgente C# che consente di esportare il contenuto in un file Markdown con l'allineamento del contenuto della tabella utilizzando la libreria Aspose.Words per .NET. Assicurati di aver incluso la libreria Aspose.Words nel tuo progetto prima di utilizzare questo codice.

## Passaggio 1: impostare il percorso della directory del documento

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Assicurati di specificare il percorso corretto della directory dei documenti in cui verrà salvato il documento modificato.

## Passaggio 2: creare un documento e un generatore di documenti

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Qui creiamo un'istanza di`Document` class e un'istanza di`DocumentBuilder` class che ci permetterà di manipolare il documento e aggiungere elementi.

## Passaggio 3: inserisci le celle nella tabella con diversi allineamenti di paragrafo

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Usiamo il Document Builder per inserire celle nella tabella e impostare diversi allineamenti di paragrafo per ogni cella.

## Passaggio 4: imposta le opzioni di esportazione Markdown e salva il documento modificato

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

Impostiamo le opzioni di esportazione Markdown con diversi allineamenti del contenuto della tabella, quindi salviamo il documento modificato utilizzando ciascuna opzione di allineamento.

### Esempio di codice sorgente da esportare in Markdown con l'allineamento del contenuto della tabella utilizzando Aspose.Words per .NET

```csharp

            
	// Il percorso della directory dei documenti.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Rende allineati tutti i paragrafi all'interno della tabella.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// L'allineamento in questo caso verrà preso dal primo paragrafo nella corrispondente colonna della tabella.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Salva il documento modificato
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
