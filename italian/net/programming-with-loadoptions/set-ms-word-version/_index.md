---
title: Imposta la versione di MS Word
linktitle: Imposta la versione di MS Word
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come caricare un documento con una versione specifica di MS Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-loadoptions/set-ms-word-version/
---

Quando si lavora con documenti Word in un'applicazione C#, potrebbe essere necessario specificare la versione di Microsoft Word da utilizzare durante il caricamento del documento. Con la libreria Aspose.Words per .NET, puoi facilmente impostare quale versione di MS Word utilizzare utilizzando LoadOptions. In questa guida dettagliata, ti illustreremo come utilizzare Aspose.Words per il codice sorgente .NET C# per caricare un documento con una versione specifica di MS Word utilizzando le opzioni di caricamento di LoadOptions.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una potente libreria per creare, modificare, convertire e proteggere documenti Word in diverse piattaforme, incluso .NET. Offre molte funzionalità per la manipolazione dei documenti, come l'inserimento di testo, la modifica della formattazione, l'aggiunta di sezioni e molto altro.

## Configurazione delle opzioni di caricamento

Il primo passo è configurare le opzioni di caricamento per il nostro documento. Utilizzare la classe LoadOptions per specificare i parametri di caricamento. Nel nostro caso, dobbiamo impostare la proprietà MswVersion sulla versione desiderata di MS Word. Ad esempio, stiamo utilizzando la versione di Microsoft Word 2010. Ecco come farlo:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Creiamo un nuovo oggetto LoadOptions e impostiamo la proprietà MswVersion su MsWordVersion.Word2010 per specificare la versione di MS Word 2010.

## Caricamento del documento con la versione specificata di MS Word

Ora che abbiamo configurato le opzioni di caricamento, possiamo caricare il documento utilizzando la classe Document e specificare le opzioni di caricamento. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

In questo esempio, carichiamo il documento "Document.docx" situato nella directory dei documenti utilizzando le opzioni di caricamento specificate.

### Esempio di codice sorgente per LoadOptions con la funzionalità "Imposta versione MS Word" utilizzando Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configura le opzioni di caricamento con la funzione "Imposta versione MS Word".
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Carica il documento con la versione specificata di MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Salva il documento
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Conclusione

In questa guida, abbiamo spiegato come caricare un documento specificando una versione specifica di MS Word utilizzando la libreria Aspose.Words per .NET. Seguendo i passaggi forniti e utilizzando il codice sorgente C# fornito, è possibile applicare facilmente questa funzionalità nell'applicazione C#. Il caricamento di un documento con una versione specifica di MS Word consente di garantire la corretta compatibilità ed elaborazione del documento nella propria applicazione.
