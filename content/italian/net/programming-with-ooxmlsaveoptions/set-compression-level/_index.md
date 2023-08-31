---
title: Imposta il livello di compressione
linktitle: Imposta il livello di compressione
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come impostare il livello di compressione durante il salvataggio di un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
In questo tutorial, esploreremo il codice sorgente C# fornito per impostare il livello di compressione durante il salvataggio di un documento utilizzando Aspose.Words per .NET. Questa funzione consente di controllare il livello di compressione del documento generato.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver impostato il tuo ambiente di sviluppo con Aspose.Words per .NET. Assicurati di aver aggiunto i riferimenti necessari e importato gli spazi dei nomi appropriati.

## Passaggio 2: caricamento del documento

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 In questo passaggio, carichiamo il documento utilizzando il file`Document` metodo e passando il percorso al file DOCX da caricare.

## Passaggio 3: configurazione delle opzioni di backup OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 In questo passaggio, configuriamo le opzioni di salvataggio OOXML utilizzando il file`OoxmlSaveOptions` classe. Impostiamo il livello di compressione su`SuperFast` per ottenere una compressione più rapida.

## Passaggio 4: salvare il documento con il livello di compressione specificato

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 In quest'ultimo passaggio, salviamo il documento utilizzando il file`Save` metodo e passando il percorso al file di output con l'estensione`.docx` estensione, insieme alle opzioni di salvataggio specificate.

Ora puoi eseguire il codice sorgente per impostare il livello di compressione durante il salvataggio di un documento. Il file risultante verrà salvato nella directory specificata con il nome "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### Esempio di codice sorgente per Imposta livello di compressione utilizzando Aspose.Words per .NET 

```csharp

//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Conclusione

In questo tutorial, abbiamo esplorato la funzionalità di impostazione del livello di compressione durante il salvataggio di un documento utilizzando Aspose.Words per .NET. Specificando il livello di compressione appropriato, è possibile ottimizzare le dimensioni del documento e la velocità di generazione.

 IL`OoxmlSaveOptions`offre flessibilità per controllare il livello di compressione impostando il file`CompressionLevel` proprietà a un valore appropriato, ad esempio`SuperFast`. Ciò ti consente di trovare il giusto equilibrio tra dimensione del file e velocità di backup in base alle tue esigenze specifiche.

L'utilizzo della compressione può essere vantaggioso quando è necessario ridurre le dimensioni dei file generati, in particolare per documenti di grandi dimensioni. Ciò può semplificare l'archiviazione, la condivisione e la trasmissione di documenti.

Aspose.Words per .NET offre una gamma di potenti opzioni e funzionalità per la manipolazione dei documenti. Utilizzando le opzioni di backup appropriate, è possibile personalizzare il processo di generazione dei documenti e ottimizzare le prestazioni dell'applicazione.

Sentiti libero di esplorare più funzionalità di Aspose.Words per .NET per migliorare il flusso di lavoro di generazione dei documenti.
