---
title: Mantieni i caratteri di controllo legacy
linktitle: Mantieni i caratteri di controllo legacy
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come preservare i caratteri di controllo legacy quando salvi un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

In questo tutorial esploreremo il codice sorgente C# fornito per preservare i caratteri di controllo legacy durante il salvataggio di un documento utilizzando Aspose.Words per .NET. Questa funzionalità consente di preservare caratteri di controllo speciali durante la conversione o il salvataggio di un documento.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver configurato il tuo ambiente di sviluppo con Aspose.Words per .NET. Assicurati di aver aggiunto i riferimenti necessari e importato gli spazi dei nomi appropriati.

## Passaggio 2: caricamento del documento

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 In questo passaggio, carichiamo il documento utilizzando il file`Document` metodo e passando il percorso al file contenente i caratteri di controllo ereditati.

## Passaggio 3: configurazione delle opzioni di backup OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

In questo passaggio, configuriamo le opzioni di salvataggio OOXML creandone un nuovo`OoxmlSaveOptions`oggetto. Specifichiamo il formato di salvataggio desiderato (qui,`FlatOpc` ) e abilitare il`KeepLegacyControlChars` opzione per mantenere i caratteri di controllo legacy.

## Passaggio 4: salvataggio del documento con caratteri di controllo legacy

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 In quest'ultimo passaggio, salviamo il documento utilizzando il file`Save` metodo e passando il percorso del file di output con il metodo`.docx` estensione, insieme alle opzioni di salvataggio specificate.

Ora puoi eseguire il codice sorgente per preservare i caratteri di controllo legacy durante il salvataggio di un documento. Il file risultante verrà salvato nella directory specificata con il nome "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Codice sorgente di esempio per Keep Legacy Control Chars utilizzando Aspose.Words per .NET 
```csharp

// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Conclusione

In questo tutorial, abbiamo esplorato la funzionalità di preservare i caratteri di controllo legacy durante il salvataggio di un documento utilizzando Aspose.Words per .NET. Abbiamo imparato come preservare quei caratteri speciali che potrebbero essere importanti per la corretta formattazione o visualizzazione del documento.

 La conservazione dei caratteri di controllo legacy è particolarmente utile quando si elaborano testi con documenti che utilizzano funzionalità più vecchie o specifiche, come caratteri di controllo speciali. Abilitando il`KeepLegacyControlChars`opzione durante il salvataggio del documento, ti assicuri che questi caratteri vengano preservati.

Aspose.Words per .NET offre una gamma di opzioni di backup flessibili e potenti per soddisfare le esigenze di manipolazione dei documenti. Utilizzando le opzioni appropriate, è possibile personalizzare il processo di backup per preservare le caratteristiche specifiche dei propri documenti.

Sentiti libero di incorporare questa funzionalità nei tuoi progetti Aspose.Words per .NET per garantire l'integrità e la conservazione dei caratteri di controllo legacy nei tuoi documenti.