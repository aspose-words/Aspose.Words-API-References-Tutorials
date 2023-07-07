---
title: Commento di ancoraggio
linktitle: Commento di ancoraggio
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come ancorare le risposte ai commenti a testo specifico nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-comments/anchor-comment/
---

In questo tutorial completo, imparerai come ancorare le risposte ai commenti a un testo specifico in un documento di Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di associare commenti a testo specifico nei tuoi documenti.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
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

## Passaggio 2: creare un commento e aggiungere un intervallo di commenti
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

## Passaggio 3: salvare il documento
Dopo aver ancorato il commento a un testo specifico, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Esempio di codice sorgente per Anchor Comment Reply utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'ancoraggio di una risposta al commento utilizzando Aspose.Words per .NET:

```csharp
// Creare un'istanza del documento.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Crea tre oggetti Run.
// primi due eseguono del testo, mentre il terzo esegue un commento

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

### FAQ

#### D: Cos'è un'ancora di commento in Aspose.Words per .NET?

R: In Aspose.Words per .NET, un'ancora di commento è un indicatore che collega un commento a una posizione specifica in un documento.

#### D: Come posso aggiungere un'ancora di commento in un documento Aspose.Words per .NET?

R: Per aggiungere un'ancora di commento in un documento Aspose.Words per .NET, seguire i passaggi indicati nel tutorial.

#### D: Come posso accedere a un'ancora di commento esistente in Aspose.Words per .NET?

 R: È possibile accedere a un'ancora di commento esistente in Aspose.Words per .NET utilizzando il file`Comment.Anchor` proprietà.

#### D: Posso sopprimere un ancoraggio di commento in Aspose.Words per .NET?

 R: Sì, puoi rimuovere un ancoraggio di commento in Aspose.Words per .NET utilizzando il file`Comment.Remove` metodo.

#### D: Come posso modificare il testo di un commento collegato a un'ancora di commento in Aspose.Words per .NET?

R: Per modificare il testo di un commento associato a un commento di ancoraggio in Aspose.Words per .NET, è possibile accedere al`Comment.Text` proprietà del corrispondente`Comment` oggetto e modificare il testo secondo necessità.

