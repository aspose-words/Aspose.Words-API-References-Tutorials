---
title: Passa alla sezione nel documento di Word
linktitle: Passa alla sezione nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida dettagliata all'utilizzo della funzionalità Sposta nella sezione nella funzione documento Word di Aspose.Words per .NET per manipolare sezioni e paragrafi nei documenti Word.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/move-to-section/
---
In questo esempio, ti spiegheremo come utilizzare passo dopo passo la funzionalità Sposta nella sezione nel documento Word di Aspose.Words per .NET utilizzando il codice sorgente C# fornito. Questa funzionalità ti consente di navigare e manipolare diverse sezioni all'interno di un documento Word. Segui i passaggi seguenti per integrare questa funzionalità nella tua applicazione.

## Passaggio 1: crea un nuovo documento e aggiungi una sezione

Per prima cosa dobbiamo creare un nuovo documento e aggiungervi una sezione. Utilizzare il codice seguente per eseguire questo passaggio:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Questo codice crea un nuovo documento vuoto e aggiunge una sezione a questo documento.

## Passaggio 2: sposta DocumentBuilder nella seconda sezione e aggiungi testo

Successivamente, dobbiamo spostare DocumentBuilder nella seconda sezione del documento e aggiungere del testo lì. Utilizzare il codice seguente per eseguire questo passaggio:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Questo codice crea un DocumentBuilder dal documento esistente, quindi sposta il cursore da DocumentBuilder alla seconda sezione del documento. Infine, aggiunge il testo specificato a questa sezione.

## Passaggio 3: carica un documento con paragrafi esistenti

Se vuoi lavorare con un documento esistente contenente paragrafi, puoi caricare questo documento utilizzando il seguente codice:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Questo codice carica il documento specificato (sostituisci "MyDir + "Paragraphs.docx"" con il percorso effettivo del documento) e accede alla raccolta dei paragrafi dalla prima sezione del documento. La linea`Assert.AreEqual(22, paragraphs.Count);` verifica che il documento contenga 22 paragrafi.

## Passaggio 4: crea un DocumentBuilder per un documento

È possibile creare il cursore DocumentBuilder su un paragrafo specifico utilizzando gli indici di posizione.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Passaggio 5: sposta il cursore su un paragrafo specifico


È possibile spostare il cursore di DocumentBuilder su un paragrafo specifico utilizzando gli indici di posizione. Ecco come farlo:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Questo codice sposta il cursore del DocumentBuilder al terzo paragrafo della seconda sezione (paragrafo all'indice 2) e alla posizione 10. Quindi aggiunge un nuovo paragrafo con del testo e controlla che il cursore sia ben posizionato su questo nuovo paragrafo.

### Codice sorgente di esempio per Move To Move To Sezione utilizzando Aspose.Words per .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Sposta un DocumentBuilder nella seconda sezione e aggiungi testo.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Crea un documento con paragrafi.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// Quando creiamo un DocumentBuilder per un documento, il suo cursore si trova all'inizio del documento per impostazione predefinita,
// e qualsiasi contenuto aggiunto da DocumentBuilder verrà semplicemente anteposto al documento.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//Puoi spostare il cursore in qualsiasi posizione all'interno di un paragrafo.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

È tutto ! Ora hai capito come utilizzare la funzionalità di spostamento nella sezione di Aspose.Words per .NET utilizzando il codice sorgente fornito. Ora puoi integrare questa funzionalità nella tua applicazione e manipolare dinamicamente sezioni e paragrafi dei tuoi documenti Word.

## Conclusione

In questo esempio, abbiamo esplorato la funzionalità Sposta nella sezione di Aspose.Words per .NET. Abbiamo imparato come creare un nuovo documento, aggiungervi sezioni e utilizzare la classe DocumentBuilder per navigare verso sezioni e paragrafi specifici all'interno di un documento Word. Questa funzionalità fornisce agli sviluppatori potenti strumenti per manipolare il contenuto e la struttura dei documenti Word a livello di codice utilizzando Aspose.Words per .NET.

### Domande frequenti per lo spostamento nella sezione del documento Word

#### D: Qual è lo scopo della funzionalità Sposta nella sezione in Aspose.Words per .NET?

R: La funzionalità Sposta nella sezione in Aspose.Words per .NET consente agli sviluppatori di spostarsi e manipolare diverse sezioni all'interno di un documento Word a livello di codice. Fornisce la possibilità di inserire, modificare o eliminare contenuto in sezioni specifiche del documento.

#### D: Come posso spostare DocumentBuilder in una sezione specifica di un documento Word?

R: Per spostare DocumentBuilder in una sezione specifica di un documento Word, puoi utilizzare il metodo MoveToSection della classe DocumentBuilder. Questo metodo prende l'indice della sezione di destinazione come parametro e posiziona il cursore all'inizio di quella sezione.

#### D: Posso aggiungere o modificare contenuti dopo essermi spostato in una sezione specifica utilizzando la funzione Sposta nella sezione?

R: Sì, una volta posizionato DocumentBuilder nella sezione desiderata utilizzando MoveToSection, puoi utilizzare vari metodi della classe DocumentBuilder, come Writeln, Write o InsertHtml, per aggiungere o modificare il contenuto di quella sezione.

#### D: Come posso lavorare con i paragrafi esistenti in un documento utilizzando la funzione Sposta nella sezione?

R: Puoi caricare un documento esistente contenente paragrafi utilizzando il costruttore Document e quindi accedere alla raccolta di paragrafi dalla sezione desiderata utilizzando la proprietà FirstSection.Body.Paragraphs.

#### D: Posso spostare il cursore di DocumentBuilder su un paragrafo specifico all'interno di una sezione utilizzando la funzione Sposta nella sezione?

R: Sì, puoi spostare il cursore DocumentBuilder su un paragrafo specifico all'interno di una sezione utilizzando il metodo MoveToParagraph. Questo metodo prende come parametri gli indici del paragrafo di destinazione e la posizione del carattere (offset) all'interno del paragrafo.