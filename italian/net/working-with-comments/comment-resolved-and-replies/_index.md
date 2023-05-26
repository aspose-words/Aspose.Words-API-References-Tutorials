---
title: Commento risolto e risposte
linktitle: Commento risolto e risposte
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come risolvere i commenti e le loro risposte nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-comments/comment-resolved-and-replies/
---

In questo tutorial completo imparerai come risolvere i commenti e le loro risposte in un documento di Word usando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di gestire la risoluzione dei commenti e aggiornare lo stato dei commenti e le relative risposte.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: caricare il documento e accedere ai commenti
Per iniziare, carica il documento che contiene i commenti utilizzando la classe Document e accedi alla raccolta dei commenti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Passaggio 2: risolvere i commenti e le relative risposte
Successivamente, scorrere i commenti e le relative risposte per contrassegnarli come risolti:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

Nel codice sopra, accediamo al commento principale e iteriamo attraverso le sue risposte. Possiamo recuperare l'ID del commento principale e il suo stato di risoluzione. Quindi, aggiorniamo il segno "Fatto" di ogni risposta al commento per indicare la risoluzione.

## Passaggio 3: salvare il documento
Dopo aver risolto i commenti e aggiornato il loro stato, salvare il documento modificato in un file utilizzando il metodo Save della classe Document:

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
Ricorda di regolare il codice in base ai tuoi requisiti specifici, incluso il percorso del file del documento e la personalizzazione aggiuntiva

## Conclusione
Congratulazioni! Hai imparato con successo come risolvere i commenti e le loro risposte in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi gestire la risoluzione dei commenti e aggiornare lo stato dei commenti e le relative risposte in base alle tue esigenze.

La risoluzione dei commenti aiuta a tenere traccia e gestire il feedback all'interno di un documento. Sperimenta con diversi stati dei commenti e personalizzali per migliorare la collaborazione e i processi di revisione nei tuoi documenti.
