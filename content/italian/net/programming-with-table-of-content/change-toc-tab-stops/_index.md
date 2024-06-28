---
title: Cambia le tabulazioni Toc nel documento di Word
linktitle: Cambia le tabulazioni Toc nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come modificare le schede del sommario in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words per .NET è una potente libreria per creare, modificare e manipolare documenti Word in un'applicazione C#. Tra le funzionalità offerte da Aspose.Words, c'è la possibilità di modificare le schede utilizzate nell'indice di un documento Word. In questa guida, ti mostreremo come utilizzare il codice sorgente C# di Aspose.Words per .NET per modificare le schede nel sommario di un documento.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una libreria popolare che rende l'elaborazione delle parole con documenti Word semplice ed efficiente. Offre un'ampia gamma di funzionalità per creare, modificare e manipolare documenti Word, inclusa la modifica delle schede del sommario.

## Caricamento del documento contenente il sommario

Il primo passo è caricare il documento Word contenente il sommario che desideri modificare. Utilizzare la classe Document per caricare il documento dal file sorgente. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

In questo esempio, carichiamo il documento "Table of Contents.docx" che si trova nella directory dei documenti.

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

In questo esempio, stiamo utilizzando un ciclo per scorrere ogni paragrafo del documento. Controlliamo quindi se il paragrafo è formattato utilizzando gli stili dei risultati del sommario (TOC). In tal caso, accediamo alla prima scheda utilizzata in questo paragrafo e la modifichiamo rimuovendo la vecchia scheda e aggiungendo una nuova scheda con una posizione modificata.

## Salva il documento modificato

Una volta apportate le modifiche necessarie alle schede del sommario, è possibile salvare il documento modificato utilizzando il metodo Save della classe Document. Ecco un esempio:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

In questo esempio, salviamo il documento modificato come "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Codice sorgente di esempio per la funzionalità "Modifica schede del sommario" con Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Caricare il documento contenente il sommario
Document doc = new Document(dataDir + "Table of contents.docx");

// Modificare le schede del sommario
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

In questa guida, abbiamo spiegato come utilizzare Aspose.Words per .NET per modificare le schede nel sommario di un documento Word utilizzando il codice sorgente C# fornito. Seguendo i passaggi forniti, puoi personalizzare facilmente le schede del sommario nei documenti Word nell'applicazione C#. Aspose.Words offre un'enorme flessibilità e potenza per lavorare con gli stili e la formattazione dei tuoi documenti, permettendoti di creare documenti Word attraenti e professionali.

### Domande frequenti sulla modifica delle tabulazioni nel documento Word

#### D: Qual è lo scopo della funzionalità "Cambia tabulazioni nel documento Word" in Aspose.Words per .NET?

R: La funzionalità "Cambia tabulazioni nel documento Word" in Aspose.Words per .NET consente di modificare le tabulazioni utilizzate nel sommario di un documento Word. Consente di personalizzare l'allineamento e il posizionamento dei numeri di pagina e delle intestazioni corrispondenti all'interno del sommario.

#### D: Cos'è Aspose.Words per .NET?

R: Aspose.Words per .NET è una potente libreria progettata per l'elaborazione di parole con documenti Word nelle applicazioni .NET. Fornisce funzionalità complete per creare, modificare, manipolare e convertire documenti Word a livello di codice utilizzando C# o altri linguaggi .NET.

#### D: Come carico un documento Word contenente un sommario utilizzando Aspose.Words per .NET?

 R: Per caricare un documento Word contenente un sommario utilizzando Aspose.Words per .NET, è possibile utilizzare`Document` classe e il suo costruttore. Fornendo il percorso del file del documento, è possibile caricarlo in un file`Document` oggetto. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Questo frammento di codice carica il documento "Sommario.docx" situato nella directory specificata.

#### D: Come posso modificare le schede utilizzate nel sommario utilizzando Aspose.Words per .NET?

 R: Una volta caricato il documento, è possibile scorrere ogni paragrafo del documento e verificare se è formattato utilizzando gli stili di risultato del sommario (TOC). Se un paragrafo è formattato come stile sommario, puoi modificare le tabulazioni utilizzate per allineare i numeri di pagina. In Aspose.Words per .NET, puoi accedere a`ParagraphFormat` proprietà di ciascun paragrafo per recuperare e modificare le tabulazioni. Ecco un esempio:

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

In questo codice, il ciclo scorre ogni paragrafo del documento. Se un paragrafo ha uno stile sommario, accede alla prima tabulazione utilizzata in quel paragrafo, la rimuove e aggiunge una nuova tabulazione con una posizione modificata.

#### D: Posso modificare le schede per più livelli nel sommario utilizzando Aspose.Words per .NET?

R: Sì, puoi modificare le schede per più livelli nel sommario utilizzando Aspose.Words per .NET. Scorrendo ogni paragrafo e controllando lo stile del sommario, è possibile modificare le schede per ciascun livello individualmente. È possibile accedere al livello desiderato del sommario e regolare di conseguenza le tabulazioni.

#### D: Come posso salvare il documento modificato dopo aver modificato le schede nel sommario utilizzando Aspose.Words per .NET?

 R: Dopo aver apportato le modifiche necessarie alle schede del sommario, è possibile salvare il documento modificato utilizzando il file`Save` metodo del`Document` classe. Fornire il percorso file e il nome desiderati per il documento di output come parametro nel file`Save` metodo. Ecco un esempio:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Questo codice salva il documento modificato come "WorkingWithTableOfContent.ChangeTocTabStops.docx".

#### D: Posso personalizzare altri aspetti del sommario utilizzando Aspose.Words per .NET?

R: Sì, con Aspose.Words per .NET, puoi personalizzare vari aspetti del sommario. Oltre a modificare le schede, puoi modificare gli stili dei caratteri, la dimensione, l'allineamento e altre proprietà di formattazione delle voci del sommario e dei numeri di pagina. Inoltre, puoi regolare il rientro, la spaziatura e la formattazione delle intestazioni corrispondenti.

#### Q:. Posso modificare l'allineamento delle tabulazioni e i caratteri iniziali per il sommario utilizzando Aspose.Words per .NET?

R: Sì, puoi modificare l'allineamento delle tabulazioni e i caratteri iniziali per il sommario utilizzando Aspose.Words per .NET. Accedendo alle tabulazioni e regolandone l'allineamento e le proprietà della direttrice, puoi controllare l'allineamento e l'aspetto visivo dei numeri di pagina e delle intestazioni corrispondenti nel sommario.

#### D: Aspose.Words per .NET supporta la modifica di altri stili e formattazione nei documenti di Word?

R: Sì, Aspose.Words per .NET fornisce un ampio supporto per la modifica di vari stili e formattazione nei documenti di Word. Ti consente di modificare gli stili per diversi elementi come paragrafi, intestazioni, tabelle, elenchi e altro. Puoi modificare caratteri, colori, allineamento, rientro, spaziatura e altri aspetti di formattazione in base alle tue esigenze.

#### D: Posso modificare le schede nel sommario in un documento Word esistente utilizzando Aspose.Words per .NET?

R: Sì, puoi modificare le schede nel sommario in un documento Word esistente utilizzando Aspose.Words per .NET. Caricando il documento, scorrendo i paragrafi e apportando le modifiche necessarie alle tabulazioni, è possibile aggiornare le tabulazioni nel sommario. Infine, salva il documento per applicare le modifiche.