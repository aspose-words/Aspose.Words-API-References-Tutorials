---
title: Carica PDF crittografato
linktitle: Carica PDF crittografato
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per caricare un PDF crittografato utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

Quando si lavora con documenti PDF nell'applicazione .NET, potrebbe essere necessario caricare file PDF protetti da password. Aspose.Words per .NET è una potente libreria che fornisce funzionalità per il caricamento di documenti PDF crittografati. In questo articolo, ti guideremo passo dopo passo per comprendere e utilizzare questa funzione.

## Comprensione della funzione Carica PDF crittografato

La funzione Carica PDF crittografato di Aspose.Words per .NET consente di caricare file PDF protetti da password. È possibile specificare la password durante il caricamento del documento in modo da poter accedere al suo contenuto e manipolarlo secondo necessità.

## Passaggio 1: caricamento del documento PDF crittografato

Il primo passo è caricare il documento PDF crittografato nella tua applicazione. Ecco come farlo:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Assicurati di specificare il percorso corretto del file PDF crittografato nel file`dataDir` variabile.

## Passaggio 2: crittografia del documento PDF

 Se vuoi anche crittografare il tuo documento PDF, puoi farlo usando il file`PdfSaveOptions` class e specificando i dettagli di crittografia:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Questo creerà una versione crittografata del documento PDF nella directory specificata.

## Passaggio 3: salvataggio del documento PDF crittografato

Dopo aver caricato ed eventualmente crittografato il documento PDF, è possibile salvarlo in un altro formato o elaborarlo ulteriormente in base alle proprie esigenze specifiche.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Passaggio 5: caricamento del documento PDF crittografato con password

Manutenzione

 Tuttavia, se si desidera caricare il documento PDF crittografato con una password, è necessario utilizzare il file`PdfLoadOptions` class e specificare la password durante il caricamento del documento:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 Assicurati di fornire la password corretta nel file`Password` variabile.

### Esempio di codice sorgente per caricare PDF crittografato utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## Conclusione

In questo articolo, abbiamo esplorato come utilizzare la funzione Carica PDF crittografato di Aspose.Words per .NET. Hai imparato come caricare file PDF crittografati, come crittografare un documento PDF, come caricare un PDF crittografato con una password e come generare output in formato Markdown. Questa funzione è estremamente utile quando si lavora con documenti PDF protetti.


