---
title: Commento risolto e risposte
linktitle: Commento risolto e risposte
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come risolvere i commenti e le relative risposte nei documenti Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-comments/comment-resolved-and-replies/
---

In questo tutorial completo imparerai come risolvere i commenti e le loro risposte in un documento Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo gli snippet di codice C# necessari. Al termine di questa guida sarai in grado di gestire la risoluzione dei commenti e aggiornare lo stato dei commenti e le relative risposte.

## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: caricare il documento e accedere ai commenti
Per iniziare, carica il documento che contiene i commenti utilizzando la classe Document e accedi alla raccolta dei commenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Passaggio 2: risolvere i commenti e le relative risposte
Successivamente, scorri i commenti e le relative risposte per contrassegnarli come risolti:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

Nel codice precedente, accediamo al commento genitore e iteriamo attraverso le sue risposte. Possiamo recuperare l'ID del commento principale e il suo stato di risoluzione. Quindi, aggiorniamo il segno "Fine" di ciascuna risposta al commento per indicare la risoluzione.

## Passaggio 3: salva il documento
Dopo aver risolto i commenti e aggiornato il loro stato, salva il documento modificato in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Esempio di codice sorgente per la risoluzione dei commenti e delle relative risposte utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per risolvere i commenti e le loro risposte utilizzando Aspose.Words per .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Ricorda di modificare il codice in base alle tue esigenze specifiche, incluso il percorso del file del documento e ulteriori personalizzazioni

## Conclusione
Congratulazioni! Hai imparato con successo come risolvere i commenti e le loro risposte in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi gestire la risoluzione dei commenti e aggiornare lo stato dei commenti e le relative risposte in base alle tue esigenze.

La risoluzione dei commenti aiuta a tenere traccia e gestire il feedback all'interno di un documento. Sperimenta diversi stati dei commenti e personalizzali per migliorare i processi di collaborazione e revisione nei tuoi documenti.

### Domande frequenti

#### D: Come posso risolvere un commento in Aspose.Words per .NET?

 R: Per risolvere un commento in Aspose.Words per .NET, puoi utilizzare il file`Comment.Resolve` metodo che specifica il`Comment` oggetto che vuoi risolvere. Ciò contrassegnerà il commento come risolto e lo nasconderà nel documento finale.

#### D: Come posso aggiungere una risposta a un commento risolto in Aspose.Words per .NET?

 R: Sebbene i commenti risolti siano nascosti per impostazione predefinita nel documento finale, puoi comunque aggiungere una risposta a un commento risolto utilizzando il file`Comment.AddReply`metodo specificando il testo della risposta e dove vuoi aggiungerlo.

#### D: Come posso visualizzare i commenti risolti in Aspose.Words per .NET?

 R: Per impostazione predefinita, i commenti risolti sono nascosti nel documento finale. Tuttavia, puoi mostrarli utilizzando il file`CommentOptions.ShowResolvedComments` proprietà del`Document` oggetto e impostandolo su`true`.

#### D: Come posso nascondere tutti i commenti, comprese le risposte, in Aspose.Words per .NET?

 R: Per nascondere tutti i commenti, comprese le risposte, in Aspose.Words per .NET, puoi utilizzare il file`CommentOptions.CommentDisplayMode` proprietà del`Document` oggetto e impostarlo su`CommentDisplayMode.None`.

#### D: Posso modificare il testo di un commento risolto in Aspose.Words per .NET?

 R: Sì, puoi modificare il testo di un commento risolto in Aspose.Words per .NET accedendo al`Comment.Text` proprietà del corrispondente`Comment` oggetto e modificando il testo secondo necessità.