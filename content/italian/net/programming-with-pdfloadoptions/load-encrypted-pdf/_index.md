---
title: Carica PDF crittografato
linktitle: Carica PDF crittografato
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per caricare un PDF crittografato utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

Quando si elaborano parole con documenti PDF nell'applicazione .NET, potrebbe essere necessario caricare file PDF protetti da password. Aspose.Words per .NET è una potente libreria che fornisce funzionalità per il caricamento di documenti PDF crittografati. In questo articolo ti guideremo passo dopo passo per comprendere e utilizzare questa funzionalità.

## Comprensione della funzione Carica PDF crittografato

La funzione Carica PDF crittografato di Aspose.Words per .NET consente di caricare file PDF protetti da password. È possibile specificare la password durante il caricamento del documento in modo da poter accedere al suo contenuto e manipolarlo secondo necessità.

## Passaggio 1: caricamento del documento PDF crittografato

Il primo passo è caricare il documento PDF crittografato nella tua applicazione. Ecco come farlo:

```csharp
//Percorso della directory dei documenti.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Assicurati di specificare il percorso corretto del file PDF crittografato nel file`dataDir` variabile.

## Passaggio 2: crittografia del documento PDF

 Se desideri crittografare anche il tuo documento PDF, puoi farlo utilizzando il file`PdfSaveOptions` classe e specificando i dettagli di crittografia:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Ciò creerà una versione crittografata del documento PDF nella directory specificata.

## Passaggio 3: salvataggio del documento PDF crittografato

Dopo aver caricato ed eventualmente crittografato il documento PDF, puoi salvarlo in un altro formato o elaborarlo ulteriormente in base alle tue esigenze specifiche.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Passaggio 5: caricamento del documento PDF crittografato con password

Manutenzione

Tuttavia, se desideri caricare il documento PDF crittografato con una password, devi utilizzare il file`PdfLoadOptions` class e specificare la password durante il caricamento del documento:

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

In questo articolo, abbiamo esplorato come utilizzare la funzionalità Carica PDF crittografato di Aspose.Words per .NET. Hai imparato come caricare file PDF crittografati, come crittografare un documento PDF, come caricare un PDF crittografato con una password e come generare output in formato Markdown. Questa funzionalità è estremamente utile durante l'elaborazione di parole con documenti PDF protetti.


