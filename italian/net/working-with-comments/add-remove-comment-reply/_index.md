---
title: Aggiungi Rimuovi Commento Rispondi
linktitle: Aggiungi Rimuovi Commento Rispondi
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come aggiungere e rimuovere le risposte ai commenti nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-comments/add-remove-comment-reply/
---

In questo tutorial completo imparerai come aggiungere e rimuovere le risposte ai commenti in un documento di Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di gestire le risposte ai commenti e personalizzarle in base alle tue esigenze.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: caricare il documento
Per iniziare, carica il documento che contiene i commenti utilizzando la classe Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Passaggio 2: accedi al commento e gestisci le risposte
Successivamente, accedi al commento dal documento utilizzando il metodo GetChild con il parametro NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Per rimuovere una risposta dal commento, utilizzare il metodo RemoveReply e fornire l'indice di risposta desiderato:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Per aggiungere una nuova risposta al commento, utilizzare il metodo AddReply e fornire il nome dell'autore, le iniziali dell'autore, la data e l'ora e il testo della risposta:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Passaggio 3: salvare il documento
Dopo aver aggiunto o rimosso le risposte ai commenti, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Codice sorgente di esempio per aggiungere e rimuovere le risposte ai commenti utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per aggiungere e rimuovere le risposte ai commenti utilizzando Aspose.Words per .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Conclusione
Congratulazioni! Hai imparato con successo come aggiungere e rimuovere le risposte ai commenti in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata e utilizzando il codice sorgente fornito, ora puoi gestire le risposte ai commenti e personalizzarle in base alle tue esigenze.

Le risposte ai commenti consentono discussioni collaborative e feedback all'interno di un documento. Sperimenta con diversi autori di risposta, iniziali, date e testi per migliorare la collaborazione e la comunicazione all'interno dei tuoi documenti.

### FAQ

#### D: Come posso aggiungere un commento in Aspose.Words per .NET?

 R: Per aggiungere un commento in Aspose.Words per .NET, puoi utilizzare il file`Comment.AddComment` metodo specificando il testo del commento e dove si desidera aggiungerlo nel documento.

#### D: Come posso rimuovere un commento in Aspose.Words per .NET?

 R: Per rimuovere un commento in Aspose.Words per .NET, puoi utilizzare il file`Comment.Remove` metodo che specifica il`Comment` oggetto che vuoi rimuovere.

#### D: Posso rispondere a un commento in Aspose.Words per .NET?

 R: Sì, puoi rispondere a un commento in Aspose.Words per .NET utilizzando il`Comment.AddReply` metodo specificando il testo della risposta e dove si desidera aggiungerlo nel documento.

#### D: Come posso accedere ai commenti esistenti in Aspose.Words per .NET?

 R: Puoi accedere ai commenti esistenti in Aspose.Words per .NET utilizzando il file`CommentCollection`proprietà del`Document`oggetto. Questo ti permetterà di sfogliare tutti i commenti presenti nel documento.

#### D: Posso modificare il testo del commento in Aspose.Words per .NET?

 R: Sì, puoi modificare il testo di un commento in Aspose.Words per .NET accedendo a`Comment.Text` proprietà del corrispondente`Comment` oggetto e modificando il testo secondo necessità.