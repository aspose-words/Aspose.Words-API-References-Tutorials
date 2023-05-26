---
title: Cambia le tabulazioni Toc
linktitle: Cambia le tabulazioni Toc
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come modificare le schede del sommario in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words per .NET è una potente libreria per creare, modificare e manipolare documenti Word in un'applicazione C#. Tra le funzionalità offerte da Aspose.Words c'è la possibilità di modificare le schede utilizzate in un sommario di un documento Word. In questa guida, ti mostreremo come utilizzare il codice sorgente C# di Aspose.Words per .NET per modificare le schede nel sommario di un documento.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una libreria popolare che rende il lavoro con i documenti di Word facile ed efficiente. Offre una vasta gamma di funzionalità per la creazione, la modifica e la manipolazione di documenti Word, inclusa la modifica delle schede del sommario.

## Caricamento del documento contenente il sommario

Il primo passo è caricare il documento Word contenente il sommario che desideri modificare. Utilizzare la classe Document per caricare il documento dal file di origine. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

In questo esempio, carichiamo il documento "Tabella dei contenuti.docx" che si trova nella directory dei documenti.

## Modifica delle schede nel sommario

Una volta caricato il documento, esaminiamo ogni paragrafo del documento e controlliamo se è formattato utilizzando gli stili di risultato del sommario (TOC). In tal caso, modifichiamo le schede utilizzate per allineare i numeri di pagina. Ecco come:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

In questo esempio, stiamo usando un ciclo per scorrere ogni paragrafo nel documento. Verifichiamo quindi se il paragrafo è formattato utilizzando gli stili Risultato sommario (TOC). In tal caso, accediamo alla prima scheda utilizzata in questo paragrafo e la modifichiamo rimuovendo la vecchia scheda e aggiungendo una nuova scheda con una posizione modificata.

## Salva documento modificato

Una volta apportate le modifiche necessarie alle schede dell'indice, è possibile salvare il documento modificato utilizzando il metodo Save della classe Document. Ecco un esempio:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

In questo esempio, salviamo il documento modificato come "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Esempio di codice sorgente per la funzione "Modifica schede sommario" con Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento contenente il sommario
Document doc = new Document(dataDir + "Table of contents.docx");

// Modifica le schede del sommario
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Salva il documento modificato
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Conclusione

In questa guida, abbiamo spiegato come utilizzare Aspose.Words per .NET per modificare le schede nel sommario di un documento Word utilizzando il codice sorgente C# fornito. Seguendo i passaggi forniti, puoi personalizzare facilmente le schede del sommario nei tuoi documenti Word nell'applicazione C#. Aspose.Words offre un'enorme flessibilità e potenza per lavorare con gli stili e la formattazione dei tuoi documenti, permettendoti di creare documenti Word attraenti e professionali.