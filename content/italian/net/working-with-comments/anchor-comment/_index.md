---
title: Commento dell'ancora
linktitle: Commento dell'ancora
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come ancorare le risposte ai commenti a testo specifico nei documenti Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-comments/anchor-comment/
---

In questo tutorial completo imparerai come ancorare le risposte ai commenti a testo specifico in un documento Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo gli snippet di codice C# necessari. Al termine di questa guida sarai in grado di associare i commenti a testo specifico nei tuoi documenti.

## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: crea un nuovo documento e aggiungi testo
Per iniziare, crea un nuovo documento utilizzando la classe Document e aggiungi il testo desiderato:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## Passaggio 2: crea un commento e aggiungi un intervallo di commenti
Successivamente, crea un commento e associalo a un testo specifico utilizzando gli oggetti CommentRangeStart e CommentRangeEnd:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## Passaggio 3: salva il documento
Dopo aver ancorato il commento a un testo specifico, salva il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Esempio di codice sorgente per la risposta al commento di ancoraggio utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per ancorare una risposta al commento utilizzando Aspose.Words per .NET:

```csharp
// Creare un'istanza del documento.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Crea tre oggetti Esegui.
// I primi due eseguono del testo, mentre il terzo esegue un commento

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// A ciascuno degli oggetti Run è associato un oggetto CommentRangeStart e CommentRangeEnd.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### Domande frequenti

#### D: Cos'è un'ancora di commento in Aspose.Words per .NET?

R: In Aspose.Words per .NET, un'ancora di commento è un indicatore che collega un commento a una posizione specifica in un documento.

#### D: Come posso aggiungere un'ancora di commento in un documento Aspose.Words per .NET?

R: Per aggiungere un'ancora di commento in un documento Aspose.Words per .NET, seguire i passaggi indicati nel tutorial.

#### D: Come posso accedere a un ancoraggio di commento esistente in Aspose.Words per .NET?

 R: È possibile accedere a un ancoraggio di commento esistente in Aspose.Words per .NET utilizzando il file`Comment.Anchor` proprietà.

#### D: Posso sopprimere un'ancora di commento in Aspose.Words per .NET?

 R: Sì, puoi rimuovere un'ancora di commento in Aspose.Words per .NET utilizzando il file`Comment.Remove` metodo.

#### D: Come posso modificare il testo di un commento collegato a un'ancora di commento in Aspose.Words per .NET?

 A: Per modificare il testo di un commento associato a un'ancora di commento in Aspose.Words per .NET, puoi accedere a`Comment.Text` proprietà del corrispondente`Comment` oggetto e modificare il testo secondo necessità.

