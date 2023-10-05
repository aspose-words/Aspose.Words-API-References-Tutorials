---
title: Direzione del testo del documento
linktitle: Direzione del testo del documento
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come specificare la direzione del testo nei tuoi documenti con Aspose.Words per .NET. Migliora la visualizzazione per le lingue da destra a sinistra.
type: docs
weight: 10
url: /it/net/programming-with-txtloadoptions/document-text-direction/
---

In questo tutorial esploreremo il codice sorgente C# fornito per la funzionalità "Direzione del testo del documento" con Aspose.Words per .NET. Questa funzionalità ti consente di specificare la direzione del testo in un documento, il che è particolarmente utile per le lingue scritte da destra a sinistra, come l'ebraico o l'arabo.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo con Aspose.Words per .NET. Assicurati di aver aggiunto i riferimenti necessari e importato gli spazi dei nomi appropriati.

## Passaggio 2: configurazione delle opzioni di caricamento

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 In questo passaggio configuriamo le opzioni di caricamento del documento. Ne creiamo uno nuovo`TxtLoadOptions` oggetto e impostare il`DocumentDirection`proprietà a`DocumentDirection.Auto`. Questo valore indica ad Aspose.Words di determinare automaticamente la direzione del testo in base al contenuto del documento.

## Passaggio 3: caricamento del documento

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 In questo passaggio, carichiamo il documento utilizzando il file`Document` metodo e passando il percorso del file di testo da caricare. Utilizziamo anche le opzioni di caricamento specificate.

## Passaggio 4: manipola il paragrafo e visualizza la direzione del testo

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 In questo passaggio accediamo al primo paragrafo del documento utilizzando il file`FirstSection` E`Body` proprietà. Successivamente, accediamo al file`ParagraphFormat.Bidi` proprietà per ottenere la direzione del testo del paragrafo. Quindi visualizziamo questo valore nella console.

## Passaggio 5: salva il documento

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 In quest'ultimo passaggio, salviamo il documento risultante in formato .docx utilizzando il file`Save` metodo e passando il percorso al file di output.

Ora puoi eseguire il codice sorgente per caricare il documento di testo e determinare la direzione del testo. Il documento risultante verrà salvato nella directory specificata con il nome "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### Codice sorgente di esempio per la funzionalità di direzione del testo del documento con Aspose.Words per .NET.


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

In questo tutorial, abbiamo esplorato la funzionalità di direzione del testo del documento in Aspose.Words per .NET. Abbiamo imparato come specificare la direzione del testo in un documento, soprattutto per le lingue scritte da destra a sinistra, come l'ebraico o l'arabo.

Questa funzionalità è essenziale per garantire che il testo venga visualizzato correttamente nei documenti multilingue. Utilizzando le opzioni di caricamento appropriate, Aspose.Words può rilevare automaticamente la direzione del testo e applicarla al documento.

Con Aspose.Words, puoi facilmente manipolare la direzione del testo nei tuoi documenti, fornendo agli utenti un'esperienza di lettura fluida e intuitiva.

È importante notare che questa funzionalità è particolarmente utile durante l'elaborazione testi con lingue che richiedono una direzione del testo specifica. Aspose.Words semplifica questo compito fornendo potenti strumenti per gestire la direzione del testo nei tuoi documenti.

Ricordati di utilizzare le opzioni di caricamento appropriate, come l'impostazione della direzione automatica del testo, per ottenere i risultati desiderati nei tuoi documenti.

Aspose.Words per .NET offre molte funzionalità avanzate per la manipolazione e la generazione di documenti. Esplorando ulteriormente la documentazione e gli esempi forniti da Aspose.Words, sarai in grado di sfruttare appieno le capacità di questa potente libreria.

Quindi, non esitate a integrare la direzione del testo del documento nei vostri progetti Aspose.Words per .NET e sfruttare i suoi vantaggi per creare documenti multilingue attraenti e di alta qualità.