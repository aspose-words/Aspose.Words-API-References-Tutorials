---
title: Sposta in sezione
linktitle: Sposta in sezione
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata all'utilizzo di Sposta in sezione in Aspose.Words per .NET manipolare sezioni e paragrafi nei documenti di Word.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/move-to-section/
---

In questo esempio, ti illustreremo passo dopo passo come utilizzare la funzionalità Sposta in sezione di Aspose.Words per .NET utilizzando il codice sorgente C# fornito. Questa funzione consente di navigare e manipolare diverse sezioni all'interno di un documento di Word. Segui i passaggi seguenti per integrare questa funzionalità nella tua applicazione.

## Passaggio 1: crea un nuovo documento e aggiungi una sezione

Innanzitutto, dobbiamo creare un nuovo documento e aggiungervi una sezione. Utilizzare il codice seguente per eseguire questo passaggio:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Questo codice crea un nuovo documento vuoto e aggiunge una sezione a questo documento.

## Passaggio 2: sposta il DocumentBuilder nella seconda sezione e aggiungi il testo

Successivamente, dobbiamo spostare DocumentBuilder nella seconda sezione del documento e aggiungere del testo lì. Utilizzare il codice seguente per eseguire questo passaggio:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Questo codice crea un DocumentBuilder dal documento esistente, quindi sposta il cursore dal DocumentBuilder alla seconda sezione del documento. Infine, aggiunge il testo specificato a questa sezione.

## Passaggio 3: caricare un documento con paragrafi esistenti

Se vuoi lavorare con un documento esistente contenente paragrafi, puoi caricare questo documento usando il seguente codice:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Questo codice carica il documento specificato (sostituisci "MyDir + "Paragraphs.docx""con il percorso effettivo del documento) e accede alla raccolta di paragrafi dalla prima sezione del documento. La linea`Assert.AreEqual(22, paragraphs.Count);` verifica che il documento contenga 22 paragrafi.

## Passaggio 4: creare un DocumentBuilder per un documento

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

### Esempio di codice sorgente per Move To Move To Section utilizzando Aspose.Words per .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Sposta un DocumentBuilder nella seconda sezione e aggiungi del testo.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Crea un documento con paragrafi.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

//Quando creiamo un DocumentBuilder per un documento, il suo cursore si trova all'inizio del documento per impostazione predefinita,
// e qualsiasi contenuto aggiunto da DocumentBuilder verrà semplicemente anteposto al documento.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

// Puoi spostare il cursore in qualsiasi posizione all'interno di un paragrafo.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

È tutto ! Ora hai capito come utilizzare la funzionalità di passaggio alla sezione di Aspose.Words per .NET utilizzando il codice sorgente fornito. Ora puoi integrare questa funzionalità nella tua applicazione e manipolare dinamicamente sezioni e paragrafi dei tuoi documenti Word.

