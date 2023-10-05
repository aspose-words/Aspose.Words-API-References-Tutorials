---
title: Impostazione della pagina diversa
linktitle: Impostazione della pagina diversa
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere un documento con diverse impostazioni di impostazione della pagina utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/different-page-setup/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per aggiungere un documento con diverse impostazioni di impostazione della pagina a un altro documento. Il codice sorgente fornito dimostra come configurare diverse impostazioni di pagina per i documenti di origine e di destinazione e garantire la corretta continuazione e numerazione.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

-  Aspose.Words per la libreria .NET installata. Puoi scaricarlo da[Aspose.Releases]https://releases.aspose.com/words/net/ o utilizzare il gestore pacchetti NuGet per installarlo.
- Un percorso di directory di documenti in cui si trovano i documenti di origine e di destinazione.

## Passaggio 2: apri i documenti di origine e di destinazione

 Apri i documenti di origine e di destinazione utilizzando il file`Document` costruttore di classi. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: configura le impostazioni della pagina per il documento di origine

 Regola le impostazioni di impostazione della pagina del documento di origine per garantire la corretta continuazione e numerazione. In questo esempio, impostiamo l'inizio della sezione su`SectionStart.Continuous` e riavviare la numerazione delle pagine. Ci assicuriamo inoltre che la larghezza, l'altezza e l'orientamento della pagina corrispondano all'ultima sezione del documento di destinazione.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Passaggio 4: modifica la formattazione del paragrafo

 Per mantenere la formattazione corretta, scorrere tutti i paragrafi nel documento di origine e impostare il file`KeepWithNext`proprietà a`true`Ciò garantisce che i paragrafi rimangano insieme durante il processo di aggiunta.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Passaggio 5: aggiungi il documento di origine al documento di destinazione

 Usa il`AppendDocument` metodo del documento di destinazione per aggiungere il documento di origine modificato al documento di destinazione, preservando la formattazione di origine.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 6: salva il documento di destinazione

 Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Ciò completa l'implementazione dell'aggiunta di un documento con diverse impostazioni di impostazione della pagina utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per l'impostazione della pagina diversa utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Imposta il documento di origine in modo che continui subito dopo la fine del documento di destinazione.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Riavviare la numerazione delle pagine all'inizio del documento di origine.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Per garantire che ciò non accada quando il documento di origine ha impostazioni di impostazione della pagina diverse, assicurati che il file
	// le impostazioni sono identiche nell'ultima sezione del documento di destinazione.
	// Se ci sono ulteriori sezioni continue che seguono nel documento di origine,
	//questo dovrà essere ripetuto per quelle sezioni.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Scorri tutte le sezioni del documento di origine.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```