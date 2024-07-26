---
title: Accetta revisioni
linktitle: Accetta revisioni
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come accettare revisioni a un documento Word utilizzando Aspose.Words per .NET
type: docs
weight: 10
url: /it/net/working-with-revisions/accept-revisions/
---

In questo tutorial, ti guideremo attraverso l'accettazione delle revisioni di un documento Word utilizzando la funzione Accetta revisioni di Aspose.Words per .NET. Seguire i passaggi seguenti per comprendere il codice sorgente e accettare le modifiche al documento.

## Passaggio 1: aggiunta e modifica del contenuto del documento

In questo esempio, stiamo creando un documento e aggiungendo contenuto. Utilizziamo diversi paragrafi per illustrare modifiche e revisioni. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Aggiungi testo al primo paragrafo, quindi aggiungi altri due paragrafi.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Passaggio 2: monitora le recensioni e aggiungi recensioni

Abilitiamo il monitoraggio delle revisioni e aggiungiamo una revisione al documento. Ecco come:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Questo paragrafo è una revisione e avrà il flag corrispondente "IsInsertRevision" impostato.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Passaggio 3: elimina un paragrafo e gestisci le revisioni

Eliminiamo un paragrafo e controlliamo le revisioni salvate. Ecco come:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Mentre stiamo monitorando le revisioni, il paragrafo esiste ancora nel documento, avrà il flag "IsDeleteRevision" impostato
// e verrà visualizzato come recensione in Microsoft Word finché non accetteremo o rifiuteremo tutte le recensioni.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Passaggio 4: accetta le modifiche

Accettiamo tutte le modifiche al documento. Ecco come:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Passaggio 5: interrompi il monitoraggio delle recensioni

Interromperemo il monitoraggio delle revisioni in modo che le modifiche al documento non vengano più visualizzate come revisioni. Ecco come:

```csharp
doc.StopTrackRevisions();
```
## Passaggio 6: salvataggio del documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save`metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Codice sorgente di esempio per accettare revisioni utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per accettare le modifiche in un documento utilizzando Aspose.Words per .NET:


```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Aggiungi testo al primo paragrafo, quindi aggiungi altri due paragrafi.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Abbiamo tre paragrafi, nessuno dei quali registrato come alcun tipo di revisione
// Se aggiungiamo/rimuoviamo qualsiasi contenuto nel documento durante il monitoraggio delle revisioni,
// verranno visualizzati come tali nel documento e potranno essere accettati/rifiutati.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Questo paragrafo è una revisione e avrà il flag "IsInsertRevision" corrispondente impostato.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Ottieni la raccolta di paragrafi del documento e rimuovi un paragrafo.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Poiché stiamo monitorando le revisioni, il paragrafo esiste ancora nel documento, avrà il valore "IsDeleteRevision" impostato
// e verrà visualizzato come revisione in Microsoft Word, finché non accetteremo o rifiuteremo tutte le revisioni.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Il paragrafo di revisione di eliminazione viene rimosso una volta accettate le modifiche.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// L'interruzione del tracciamento delle revisioni fa sì che questo testo venga visualizzato come testo normale.
// Le revisioni non vengono conteggiate quando il documento viene modificato.
doc.StopTrackRevisions();

// Salva il documento.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Conclusione

In questo tutorial, abbiamo imparato come accettare revisioni in un documento Word utilizzando la funzionalità Accetta revisioni di Aspose.Words per .NET. Abbiamo seguito i passaggi per aggiungere e modificare il contenuto del documento, tenere traccia delle revisioni, eliminare un paragrafo rivisto, accettare tutte le modifiche e interrompere il monitoraggio delle revisioni. Ora puoi applicare queste conoscenze per gestire in modo efficace le revisioni nei tuoi documenti Word utilizzando Aspose.Words per .NET.

### Domande frequenti

#### D: Come abilito il monitoraggio delle revisioni in Aspose.Words per .NET?

#### Soluzione 1:

 R: Per abilitare il monitoraggio delle revisioni in Aspose.Words per .NET, utilizzare il file`StartTrackRevisions` metodo del`Document` oggetto e specificare il nome dell'autore e la data di inizio per il monitoraggio delle revisioni.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Soluzione 2:

 R: Puoi anche abilitare il monitoraggio delle revisioni utilizzando il file`Document` costruttore che accetta`trackRevisions`E`author` parametri.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### D: Come accettare tutte le modifiche in un documento con Aspose.Words per .NET?

 R: Usa il`AcceptAllRevisions` metodo del`Document` oggetto per accettare tutte le modifiche apportate al documento.

```csharp
doc.AcceptAllRevisions();
```

#### D: Come posso salvare un documento modificato con le revisioni accettate?

 Usa il`Save` metodo del`Document` oggetto per salvare il documento modificato con le revisioni accettate. Assicurati di fornire il percorso file corretto.

```csharp
doc.Save("path/to/the/document.docx");
```

#### D: Come posso interrompere il monitoraggio delle revisioni in Aspose.Words per .NET?

 R: Usa il`StopTrackRevisions` metodo del`Document` obiettare per interrompere le revisioni di tracciamento.

```csharp
doc.StopTrackRevisions();
```

#### D: Come posso eliminare un paragrafo rivisto in un documento con Aspose.Words per .NET?

 R: Per rimuovere un paragrafo rivisto in un documento, puoi utilizzare il file`Remove` metodo di raccolta dei paragrafi.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```