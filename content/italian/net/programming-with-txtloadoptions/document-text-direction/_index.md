---
title: Direzione del testo del documento
linktitle: Direzione del testo del documento
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come specificare la direzione del testo nei tuoi documenti con Aspose.Words per .NET. Migliora la visualizzazione per le lingue da destra a sinistra.
type: docs
weight: 10
url: /it/net/programming-with-txtloadoptions/document-text-direction/
---

In questo tutorial, esploreremo il codice sorgente C# fornito per la funzione "Document Text Direction" con Aspose.Words per .NET. Questa funzione consente di specificare la direzione del testo in un documento, particolarmente utile per le lingue scritte da destra a sinistra, come l'ebraico o l'arabo.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver impostato il tuo ambiente di sviluppo con Aspose.Words per .NET. Assicurati di aver aggiunto i riferimenti necessari e importato gli spazi dei nomi appropriati.

## Passaggio 2: configurazione delle opzioni di caricamento

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 In questo passaggio, configuriamo le opzioni di caricamento del documento. Creiamo un nuovo`TxtLoadOptions` oggetto e impostare il`DocumentDirection` proprietà a`DocumentDirection.Auto`. Questo valore indica ad Aspose.Words di determinare automaticamente la direzione del testo in base al contenuto del documento.

## Passaggio 3: caricamento del documento

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 In questo passaggio, carichiamo il documento utilizzando il file`Document` metodo e passando il percorso al file di testo da caricare. Utilizziamo anche le opzioni di caricamento specificate.

## Passaggio 4: manipolare il paragrafo e visualizzare la direzione del testo

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 In questo passaggio, accediamo al primo paragrafo del documento utilizzando il file`FirstSection` E`Body` proprietà. Successivamente, accediamo al file`ParagraphFormat.Bidi` proprietà per ottenere la direzione del testo del paragrafo. Visualizziamo quindi questo valore nella console.

## Passaggio 5: salvare il documento

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 In quest'ultimo passaggio, salviamo il documento risultante in formato .docx utilizzando il file`Save` metodo e passando il percorso al file di output.

Ora puoi eseguire il codice sorgente per caricare il documento di testo e determinare la direzione del testo. Il documento risultante verrà salvato nella directory specificata con il nome "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### Esempio di codice sorgente per la funzionalità di direzione del testo del documento con Aspose.Words per .NET.


```csharp

            
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Conclusione

In questo tutorial, abbiamo esplorato la funzione di direzione del testo del documento in Aspose.Words per .NET. Abbiamo imparato a specificare la direzione del testo in un documento, specialmente per le lingue scritte da destra a sinistra, come l'ebraico o l'arabo.

Questa funzione è essenziale per garantire che il testo venga visualizzato correttamente nei documenti multilingue. Utilizzando le opzioni di caricamento appropriate, Aspose.Words può rilevare automaticamente la direzione del testo e applicarla al documento.

Con Aspose.Words, puoi facilmente manipolare la direzione del testo nei tuoi documenti, fornendo un'esperienza di lettura fluida e intuitiva per gli utenti.

È importante notare che questa funzione è particolarmente utile durante l'elaborazione di testi con lingue che richiedono una specifica direzione del testo. Aspose.Words semplifica questo compito fornendo potenti strumenti per gestire la direzione del testo nei tuoi documenti.

Ricorda di utilizzare le opzioni di caricamento appropriate, come l'impostazione della direzione automatica del testo, per ottenere i risultati desiderati nei tuoi documenti.

Aspose.Words per .NET offre molte funzionalità avanzate per la manipolazione e la generazione di documenti. Esplorando ulteriormente la documentazione e gli esempi forniti da Aspose.Words, sarai in grado di sfruttare appieno le capacità di questa potente libreria.

Quindi, non esitare a integrare la direzione del testo del documento nei tuoi progetti Aspose.Words per .NET e approfitta dei suoi vantaggi per creare documenti multilingue attraenti e di alta qualità.