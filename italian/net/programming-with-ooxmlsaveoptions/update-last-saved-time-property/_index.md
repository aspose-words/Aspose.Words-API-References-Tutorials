---
title: Aggiorna la proprietà dell'ora dell'ultimo salvataggio
linktitle: Aggiorna la proprietà dell'ora dell'ultimo salvataggio
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come aggiornare automaticamente la proprietà Last Saved Time durante il salvataggio di un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
In questo tutorial, esploreremo il codice sorgente C# fornito per aggiornare la proprietà dell'ora dell'ultimo salvataggio durante il salvataggio di un documento utilizzando Aspose.Words per .NET. Questa funzione consente di aggiornare automaticamente la proprietà dell'ora dell'ultimo salvataggio del documento generato.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 In questo passaggio, configuriamo le opzioni di salvataggio OOXML utilizzando il file`OoxmlSaveOptions` classe. Abilitiamo l'aggiornamento automatico della proprietà dell'ora dell'ultimo salvataggio impostando`UpdateLastSavedTimeProperty` A`true`.

## Passaggio 4: salva il documento con la proprietà aggiornata

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 In quest'ultimo passaggio, salviamo il documento utilizzando il file`Save` metodo e passando il percorso al file di output con l'estensione`.docx` estensione, insieme alle opzioni di salvataggio specificate.

Ora puoi eseguire il codice sorgente per aggiornare automaticamente la proprietà dell'ora dell'ultimo salvataggio durante il salvataggio di un documento. Il file risultante verrà salvato nella directory specificata con il nome "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Codice sorgente di esempio per l'aggiornamento della proprietà dell'ora dell'ultimo salvataggio utilizzando Aspose.Words per .NET 

```csharp

//Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Conclusione

In questo tutorial, abbiamo esplorato la funzionalità di aggiornamento automatico della proprietà dell'ora dell'ultimo salvataggio durante il salvataggio di un documento utilizzando Aspose.Words per .NET. Abilitando questa funzione con le opzioni di salvataggio OOXML, puoi assicurarti che la proprietà dell'ora dell'ultimo salvataggio venga aggiornata automaticamente nel documento generato.

L'aggiornamento della proprietà dell'ora dell'ultimo salvataggio può essere utile per tenere traccia delle modifiche e delle versioni di un documento. Tiene anche traccia dell'ultimo salvataggio del documento, che può essere utile in vari scenari.

Aspose.Words per .NET semplifica l'aggiornamento automatico della proprietà Last Backup Time fornendo opzioni di backup flessibili e potenti. Puoi integrare questa funzione nei tuoi progetti per assicurarti che i documenti generati abbiano informazioni di backup accurate.