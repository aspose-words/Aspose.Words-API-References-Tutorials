---
title: Evita di incorporare i caratteri principali
linktitle: Evita di incorporare i caratteri principali
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come evitare l'incorporamento di caratteri di base durante la conversione di documenti Word in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzione Evita l'incorporamento dei caratteri di base con Aspose.Words per .NET. Questa funzione consente di controllare se i caratteri di base come Arial, Times New Roman, ecc. devono essere incorporati nel PDF durante la conversione di un documento Word. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento

Inizia caricando il documento Word che vuoi convertire in PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assicurati di specificare il percorso corretto del tuo documento Word.

## Passaggio 2: imposta le opzioni di conversione PDF

Crea un'istanza della classe PdfSaveOptions e abilita l'evitamento dell'incorporamento dei caratteri di base:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Questa opzione controlla se i font di base devono essere incorporati o meno nel PDF.

## Passo 3: Converti documento in PDF

 Usa il`Save` metodo per convertire il documento Word in PDF specificando le opzioni di conversione:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Codice sorgente di esempio per Evitare l'incorporamento di caratteri principali utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per utilizzare la funzione per evitare l'incorporamento dei caratteri principali con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Il PDF di output non verrà incorporato con caratteri principali come Arial, Times New Roman ecc.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Seguendo questi passaggi, puoi facilmente controllare se i caratteri di base devono essere incorporati nel PDF durante la conversione di un documento Word con Aspose.Words per .NET.

