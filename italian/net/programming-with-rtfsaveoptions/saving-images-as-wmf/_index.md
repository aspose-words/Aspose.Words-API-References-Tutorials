---
title: Salvare le immagini come WMF
linktitle: Salvare le immagini come WMF
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come salvare le immagini come WMF durante la conversione in RTF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-rtfsaveoptions/saving-images-as-wmf/
---

In questo tutorial, esploreremo il codice sorgente C# fornito per la funzione "Salvataggio di immagini come WMF con opzioni di salvataggio RTF" con Aspose.Words per .NET. Questa funzione consente di salvare le immagini dei documenti nel formato Windows Metafile (WMF) durante la conversione in formato RTF.

## Passaggio 1: configurazione dell'ambiente

Prima di iniziare, assicurati di aver impostato il tuo ambiente di sviluppo con Aspose.Words per .NET. Assicurati di aver aggiunto i riferimenti necessari e importato gli spazi dei nomi appropriati.

## Passaggio 2: caricamento del documento

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 In questo passaggio, carichiamo il documento utilizzando il file`Document` metodo e passando il percorso al file DOCX da caricare.

## Passaggio 3: configurazione delle opzioni di backup

```csharp
RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };
```

In questo passaggio, configuriamo le opzioni di backup RTF. Creiamo un nuovo`RtfSaveOptions` oggetto e impostare il`SaveImagesAsWmf` proprietà a`true`. Questo dice ad Aspose.Words di salvare le immagini del documento come WMF durante la conversione in RTF.

## Passaggio 4: salvare il documento

```csharp
doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```

 In quest'ultimo passaggio, salviamo il documento risultante in formato RTF utilizzando il file`Save` metodo e passando il percorso al file di output, insieme alle opzioni di salvataggio specificate.

Ora puoi eseguire il codice sorgente per salvare le immagini dei documenti in formato WMF durante la conversione in formato RTF. Il documento risultante verrà salvato nella directory specificata con il nome "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf".

### Esempio di codice sorgente per funzionalità di salvataggio di immagini WMF con opzioni di salvataggio RTF con Aspose.Words per .NET".

```csharp

            
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");

RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };

doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
            
        
```
## Conclusione

In questo tutorial, abbiamo esplorato la funzionalità di salvataggio delle immagini come WMF con le opzioni di salvataggio RTF in Aspose.Words per .NET. Abbiamo imparato come salvare le immagini da un documento in formato WMF durante la conversione in formato RTF.

Questa funzione è utile quando si desidera mantenere la qualità e la risoluzione delle immagini nei documenti RTF. Salvando le immagini in formato WMF, puoi assicurarti che il loro aspetto e la loro nitidezza rimangano intatti.

Aspose.Words per .NET offre molte funzionalità avanzate per la manipolazione e la generazione di documenti. Il salvataggio delle immagini in formato WMF durante la conversione in formato RTF è uno dei tanti potenti strumenti che ti offre.