---
title: Costruisci tabella nel documento Word
linktitle: Costruisci tabella nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come creare una tabella in un documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/build-table/
---
In questo tutorial passo passo imparerai come creare una tabella in un documento Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo gli snippet di codice C# necessari. Al termine di questa guida sarai in grado di creare una tabella con formattazione e contenuto personalizzati utilizzando la classe DocumentBuilder.

## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: crea un nuovo documento
Per iniziare, crea un nuovo documento utilizzando la classe Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: avvia la tabella
Successivamente, utilizza il metodo StartTable della classe DocumentBuilder per iniziare a creare la tabella:

```csharp
Table table = builder.StartTable();
```

## Passaggio 3: inserisci celle e aggiungi contenuto
Ora puoi inserire celle nella tabella e aggiungere contenuto utilizzando i metodi InsertCell e Write della classe DocumentBuilder. Personalizza la formattazione della cella secondo necessità:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Passaggio 4: termina la riga
Dopo aver aggiunto il contenuto alle celle della prima riga, utilizza il metodo EndRow della classe DocumentBuilder per terminare la riga:

```csharp
builder.EndRow();
```

## Passaggio 5: personalizzare la formattazione della riga
È possibile personalizzare la formattazione di una riga impostando le proprietà degli oggetti RowFormat e CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Passaggio 6: termina la tabella
Per completare la tabella utilizzare il metodo EndTable della classe DocumentBuilder:

```csharp
builder.EndTable();
```

### Esempio di codice sorgente per creare una tabella utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per creare una tabella utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Conclusione
Congratulazioni! Hai imparato con successo come creare una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi creare tabelle con formattazione personalizzata.

### Domande frequenti sulla tabella di creazione nel documento Word

#### D: Cos'è Aspose.Words per .NET?

R: Aspose.Words per .NET è una potente libreria di elaborazione documenti che consente agli sviluppatori di creare, leggere, modificare e convertire documenti Microsoft Word a livello di codice in applicazioni .NET. Fornisce un'ampia gamma di funzionalità per lavorare con documenti Word, come manipolazione del testo, creazione di tabelle, protezione dei documenti, formattazione e altro.

#### D: Come posso creare una tabella in un documento Word utilizzando Aspose.Words per .NET?

R: Per creare una tabella in un documento di Word utilizzando Aspose.Words per .NET, puoi seguire questi passaggi:
1.  Crea una nuova istanza di`Document` classe e a`DocumentBuilder` oggetto.
2.  Usa il`StartTable` metodo del`DocumentBuilder`classe per iniziare a costruire la tabella.
3.  Inserisci celle nella tabella e aggiungi contenuto utilizzando il comando`InsertCell` E`Write` metodi del`DocumentBuilder` classe.
4.  Termina la riga utilizzando il`EndRow` metodo del`DocumentBuilder` classe.
5.  Personalizza la formattazione delle righe impostando le proprietà del file`RowFormat` E`CellFormat` oggetti.
6.  Termina la tabella utilizzando il`EndTable` metodo del`DocumentBuilder` classe.
7. Salva il documento.

#### D: Come posso personalizzare la formattazione della tabella e delle sue celle?

 R: Puoi personalizzare la formattazione della tabella e delle sue celle impostando varie proprietà del file`RowFormat` E`CellFormat` oggetti. Ad esempio, puoi regolare l'allineamento delle celle, l'orientamento verticale e orizzontale del testo, l'altezza della cella, l'altezza della riga e altro ancora. Utilizzando queste proprietà è possibile ottenere l'aspetto desiderato per la tabella e il relativo contenuto.

#### D: Posso creare tabelle complesse con celle unite e altre funzionalità avanzate?

 R: Sì, Aspose.Words per .NET fornisce funzionalità avanzate per creare tabelle complesse, incluso il supporto per celle unite, tabelle nidificate e layout di tabelle complessi. Puoi usare il`MergeCells` metodo per unire le celle,`StartTable`metodo per creare tabelle nidificate e altri metodi per ottenere la struttura della tabella desiderata.

#### D: Aspose.Words per .NET è compatibile con diversi formati di documenti Word?

R: Sì, Aspose.Words per .NET è compatibile con vari formati di documenti Word, inclusi DOC, DOCX, RTF e altri. Supporta sia i formati legacy (DOC) che i moderni formati basati su XML (DOCX) e ti consente di lavorare con documenti in diversi formati senza problemi.

#### D: Dove posso trovare ulteriori informazioni e documentazione per Aspose.Words per .NET?

 R: Puoi trovare documentazione completa ed esempi di codice su[Riferimenti API](https://reference.aspose.com/words/net/). La documentazione fornirà informazioni dettagliate sulle funzionalità della libreria e su come utilizzarle nelle applicazioni .NET.