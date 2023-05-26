---
title: Carica documento crittografato
linktitle: Carica documento crittografato
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come caricare e salvare documenti crittografati con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-loadoptions/load-encrypted-document/
---

Quando si lavora con documenti crittografati in un'applicazione C#, è importante poterli caricare correttamente fornendo la password corretta. Con la libreria Aspose.Words per .NET, puoi caricare facilmente documenti crittografati utilizzando le opzioni di caricamento appropriate. In questa guida dettagliata, ti mostreremo come utilizzare il codice sorgente C# di Aspose.Words per .NET per caricare un documento crittografato utilizzando le opzioni di caricamento LoadOptions.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una potente libreria per creare, modificare, convertire e proteggere documenti Word in diverse piattaforme, incluso .NET. Offre molte funzionalità per la manipolazione dei documenti, come l'inserimento di testo, la modifica della formattazione, l'aggiunta di sezioni e molto altro.

## Caricamento di un documento crittografato

Il primo passaggio consiste nel caricare un documento crittografato utilizzando le opzioni di caricamento appropriate. Nel nostro caso, utilizziamo la classe Document per caricare il documento specificando il percorso del documento e la password. Ecco un esempio:

```csharp
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));
```

In questo esempio, carichiamo il documento "Encrypted.docx" che si trova nella directory dei documenti utilizzando la password "password".

## Salvataggio di un documento crittografato

Dopo aver caricato un documento crittografato, puoi anche salvarlo specificando una nuova password per il file di output. Nel nostro esempio, utilizziamo la classe OdtSaveOptions per salvare il documento in formato ODT con una nuova password. Ecco come farlo:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

In questo esempio, salviamo il documento con il nome "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt" specificando la nuova password "newpassword".

### Esempio di codice sorgente per LoadOptions con la funzionalità "Carica documento crittografato" utilizzando Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica un documento crittografato con la password specificata
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));

//Salva un documento crittografato con una nuova password
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

## Conclusione

In questa guida, abbiamo spiegato come caricare e salvare documenti crittografati utilizzando la libreria Aspose.Words per .NET. Seguendo i passaggi forniti e usando il codice sorgente C# fornito, puoi facilmente applicare questa funzionalità nella tua applicazione C#. Il caricamento di documenti crittografati mantiene i tuoi dati al sicuro e ti consente di lavorare con documenti protetti in Aspose.Words.