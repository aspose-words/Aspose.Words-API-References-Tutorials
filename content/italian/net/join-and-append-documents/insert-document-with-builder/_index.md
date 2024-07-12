---
title: Inserisci documento con Builder
linktitle: Inserisci documento con Builder
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come unire due documenti Word utilizzando Aspose.Words per .NET. Guida passo passo per inserire un documento con DocumentBuilder e preservare la formattazione.
type: docs
weight: 10
url: /it/net/join-and-append-documents/insert-document-with-builder/
---
## introduzione

Quindi, hai due documenti Word e stai cercando di unirli in uno solo. Potresti pensare: "Esiste un modo semplice per farlo a livello di programmazione?" Assolutamente! Oggi ti guiderò attraverso il processo di inserimento di un documento in un altro utilizzando la libreria Aspose.Words per .NET. Questo metodo è molto utile, soprattutto quando hai a che fare con documenti di grandi dimensioni o devi automatizzare il processo. Immergiamoci subito!

## Prerequisiti

Prima di iniziare, assicuriamoci di avere tutto ciò di cui hai bisogno:

1.  Aspose.Words per .NET: se non lo hai già fatto, puoi scaricarlo da[Qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: assicurati di avere Visual Studio o qualsiasi altro IDE adatto installato.
3. Conoscenza di base di C#: un po' di familiarità con C# sarà molto utile.

## Importa spazi dei nomi

Per prima cosa, devi importare gli spazi dei nomi necessari per accedere alle funzionalità della libreria Aspose.Words. Ecco come puoi farlo:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Ora che abbiamo i prerequisiti, analizziamo il processo passo dopo passo.

## Passaggio 1: impostazione della directory dei documenti

Prima di iniziare a scrivere il codice, devi impostare il percorso della directory dei documenti. Qui è dove vengono archiviati i documenti di origine e di destinazione.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo in cui si trovano i tuoi documenti. Ciò aiuterà il programma a trovare facilmente i tuoi file.

## Passaggio 2: caricamento dei documenti di origine e di destinazione

Successivamente, dobbiamo caricare i documenti con cui vogliamo lavorare. In questo esempio, abbiamo un documento di origine e un documento di destinazione.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

 Qui stiamo usando il`Document` classe dalla libreria Aspose.Words per caricare i nostri documenti. Assicurati che i nomi dei file corrispondano a quelli nella tua directory.

## Passaggio 3: creazione di un oggetto DocumentBuilder

 IL`DocumentBuilder` class è un potente strumento nella libreria Aspose.Words. Ci consente di navigare e manipolare il documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

 In questo passaggio, abbiamo creato un file`DocumentBuilder` oggetto per il nostro documento di destinazione. Questo ci aiuterà a inserire il contenuto nel documento.

## Passaggio 4: spostarsi alla fine del documento

Dobbiamo spostare il cursore del generatore alla fine del documento di destinazione prima di inserire il documento di origine.

```csharp
builder.MoveToDocumentEnd();
```

Ciò garantisce che il documento di origine venga inserito alla fine del documento di destinazione.

## Passaggio 5: inserimento di un'interruzione di pagina

Per mantenere le cose in ordine, aggiungiamo un'interruzione di pagina prima di inserire il documento di origine. Ciò avvierà il contenuto del documento di origine su una nuova pagina.

```csharp
builder.InsertBreak(BreakType.PageBreak);
```

Un'interruzione di pagina garantisce che il contenuto del documento di origine inizi su una nuova pagina, conferendo al documento unito un aspetto professionale.

## Passaggio 6: inserimento del documento di origine

Ora arriva la parte emozionante: inserire effettivamente il documento di origine nel documento di destinazione.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

 Usando il`InsertDocument` metodo, possiamo inserire l'intero documento di origine nel documento di destinazione. IL`ImportFormatMode.KeepSourceFormatting` garantisce che la formattazione del documento di origine venga preservata.

## Passaggio 7: salvataggio del documento unito

Infine, salviamo il documento unito. Ciò combinerà i documenti di origine e di destinazione in un unico file.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Salvando il documento, completiamo il processo di unione dei due documenti. Il tuo nuovo documento è ora pronto e salvato nella directory specificata.

## Conclusione

E il gioco è fatto! Hai inserito con successo un documento in un altro utilizzando Aspose.Words per .NET. Questo metodo non solo è efficiente ma preserva anche la formattazione di entrambi i documenti, garantendo un'unione perfetta. Sia che tu stia lavorando su un progetto una tantum o che tu abbia bisogno di automatizzare l'elaborazione dei documenti, Aspose.Words per .NET ti copre.

## Domande frequenti

### Cos'è Aspose.Words per .NET?  
Aspose.Words per .NET è una potente libreria che consente agli sviluppatori di creare, modificare, convertire e manipolare documenti Word a livello di codice.

### Posso mantenere la formattazione del documento di origine?  
 Sì, utilizzando`ImportFormatMode.KeepSourceFormatting`, la formattazione del documento di origine viene preservata quando viene inserito nel documento di destinazione.

### Ho bisogno di una licenza per utilizzare Aspose.Words per .NET?  
 Sì, Aspose.Words per .NET richiede una licenza per la piena funzionalità. Puoi ottenere un[licenza temporanea](https://purchase.aspose.com/temporary-license/) Per la valutazione.

### Posso automatizzare questo processo?  
Assolutamente! Il metodo descritto può essere incorporato in applicazioni più grandi per automatizzare le attività di elaborazione dei documenti.

### Dove posso trovare più risorse e supporto?  
Per ulteriori informazioni, è possibile controllare il[documentazione](https://reference.aspose.com/words/net/) o visitare il[Forum di assistenza](https://forum.aspose.com/c/words/8) per assistenza.