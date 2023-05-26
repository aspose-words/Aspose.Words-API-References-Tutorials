---
title: Accetta revisioni
linktitle: Accetta revisioni
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come accettare le revisioni di un documento Word utilizzando Aspose.Words per .NET
type: docs
weight: 10
url: /it/net/working-with-revisions/accept-revisions/
---

In questo tutorial, ti guideremo attraverso l'accettazione delle revisioni di un documento Word utilizzando la funzione Accetta revisioni di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e accettare le modifiche al documento.

## Passaggio 1: aggiunta e modifica del contenuto del documento

In questo esempio, stiamo creando un documento e aggiungendo contenuto. Utilizziamo diversi paragrafi per illustrare modifiche e revisioni. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Aggiungi del testo al primo paragrafo, quindi aggiungi altri due paragrafi.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Passaggio 2: tieni traccia delle recensioni e aggiungi recensioni

Abilitiamo il monitoraggio delle revisioni e aggiungiamo una revisione al documento. Ecco come:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

//Questo paragrafo è una revisione e avrà il corrispondente flag "IsInsertRevision" impostato.
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

// Poiché stiamo monitorando le revisioni, il paragrafo esiste ancora nel documento, avrà il flag "IsDeleteRevision" impostato
// e verrà visualizzato come recensione in Microsoft Word, fino a quando non accettiamo o rifiutiamo tutte le recensioni.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Passaggio 4: accettare le modifiche

Accettiamo tutte le modifiche al documento. Ecco come:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Passaggio 5: interrompere il monitoraggio delle recensioni

Interromperemo il monitoraggio delle revisioni in modo che le modifiche al documento non vengano più visualizzate come revisioni. Ecco come:

```csharp
doc.StopTrackRevisions();
```
## Passaggio 6: salvare il documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Esempio di codice sorgente per Accetta revisioni utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per accettare le modifiche in un documento utilizzando Aspose.Words per .NET:


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Body body = doc.FirstSection.Body;
	Paragraph para = body.FirstParagraph;

	// Aggiungi del testo al primo paragrafo, quindi aggiungi altri due paragrafi.
	para.AppendChild(new Run(doc, "Paragraph 1. "));
	body.AppendParagraph("Paragraph 2. ");
	body.AppendParagraph("Paragraph 3. ");

	// Abbiamo tre paragrafi, nessuno dei quali registrato come alcun tipo di revisione
	//Se aggiungiamo/rimuoviamo qualsiasi contenuto nel documento durante il monitoraggio delle revisioni,
	// verranno visualizzati come tali nel documento e potranno essere accettati/rifiutati.
	doc.StartTrackRevisions("John Doe", DateTime.Now);

	// Questo paragrafo è una revisione e avrà il corrispondente flag "IsInsertRevision" impostato.
	para = body.AppendParagraph("Paragraph 4. ");
	Assert.True(para.IsInsertRevision);

	// Ottieni la raccolta di paragrafi del documento e rimuovi un paragrafo.
	ParagraphCollection paragraphs = body.Paragraphs;
	Assert.AreEqual(4, paragraphs.Count);
	para = paragraphs[2];
	para.Remove();

	// Poiché stiamo monitorando le revisioni, il paragrafo esiste ancora nel documento, avrà l'impostazione "IsDeleteRevision"
	// e verrà visualizzato come revisione in Microsoft Word, fino a quando non accettiamo o rifiutiamo tutte le revisioni.
	Assert.AreEqual(4, paragraphs.Count);
	Assert.True(para.IsDeleteRevision);

	// Il paragrafo di eliminazione della revisione viene rimosso una volta accettate le modifiche.
	doc.AcceptAllRevisions();
	Assert.AreEqual(3, paragraphs.Count);
	Assert.That(para, Is.Empty);

	// L'interruzione del monitoraggio delle revisioni fa apparire questo testo come testo normale.
	// Le revisioni non vengono conteggiate quando il documento viene modificato.
	doc.StopTrackRevisions();

	// Salva il documento.
	doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
            
```
