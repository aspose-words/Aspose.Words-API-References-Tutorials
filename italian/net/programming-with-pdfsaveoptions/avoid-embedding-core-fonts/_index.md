---
title: Riduci le dimensioni del file PDF non incorporando i caratteri principali
linktitle: Riduci le dimensioni del file PDF non incorporando i caratteri principali
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come ridurre le dimensioni del file PDF non incorporando i caratteri principali durante la conversione di documenti Word in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

In questo tutorial, ti guideremo attraverso i passaggi su come ridurre le dimensioni del file PDF non incorporando i caratteri principali con Aspose.Words per .NET. Questa funzione consente di controllare se i caratteri di base come Arial, Times New Roman, ecc. devono essere incorporati nel PDF durante la conversione di un documento Word. Segui i passaggi seguenti:

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


## Conclusione

In questo tutorial, abbiamo spiegato come ridurre le dimensioni di un file PDF non incorporando caratteri di base con Aspose.Words per .NET. Questa funzione consente di controllare se i caratteri di base devono essere incorporati nel PDF durante la conversione di un documento Word. Seguendo i passaggi descritti, puoi facilmente controllare l'incorporamento o il non incorporamento dei caratteri di base, che possono aiutare a ridurre le dimensioni del file PDF e garantire una migliore compatibilità e un aspetto coerente del documento su diversi dispositivi e piattaforme. Non dimenticare di considerare le conseguenze della mancata incorporazione dei caratteri di base e di sperimentare per garantire che il documento venga visualizzato come previsto.

### Domande frequenti

#### D: Qual è l'opzione per non incorporare i font di base in un file PDF e perché è importante?
R: L'opzione per non incorporare i caratteri di base in un file PDF controlla se i caratteri di base come Arial, Times New Roman, ecc. devono essere incorporati nel PDF durante la conversione di un documento Word. Questo può essere importante per ridurre le dimensioni del file PDF evitando di includere caratteri comunemente disponibili sui sistemi di lettura PDF. Può anche aiutare a garantire una migliore compatibilità e un aspetto coerente del documento PDF su diversi dispositivi e piattaforme.

#### D: Come posso configurare Aspose.Words per .NET per non incorporare font di base in un file PDF?
R: Per configurare Aspose.Words per .NET in modo che non incorpori i font principali in un file PDF, segui questi passaggi:

 Imposta il percorso della directory in cui si trovano i tuoi documenti sostituendo`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory dei documenti.

 Carica il documento Word che desideri convertire in PDF utilizzando il file`Document` class e il percorso del documento specificato.

 Crea un'istanza di`PdfSaveOptions`classe e impostare il`UseCoreFonts` proprietà a`true`. Ciò eviterà l'incorporamento di caratteri di base nel file PDF generato.

 Usa il`Save` metodo del`Document` oggetto di salvare il documento in formato PDF specificando le opzioni di conversione configurate in precedenza.

#### D: Quali sono i vantaggi di non incorporare font di base in un file PDF?
R: I vantaggi di non incorporare font di base in un file PDF sono:

Riduzione delle dimensioni del file PDF: evitando di incorporare caratteri comunemente disponibili come Arial, Times New Roman, ecc., è possibile ridurre le dimensioni del file PDF, facilitando l'archiviazione, la condivisione e il trasferimento dei file .

Migliore compatibilità: utilizzando i caratteri di base comunemente disponibili sui sistemi di lettura PDF, garantisci una migliore compatibilità e aspetto del documento su diversi dispositivi e piattaforme.

#### D: Quali sono le conseguenze se non si incorporano i font di base in un file PDF?
R: Le conseguenze della mancata incorporazione dei font di base in un file PDF sono le seguenti:

Aspetto diverso: se i caratteri di base non sono disponibili sul sistema in cui viene aperto il PDF, verranno utilizzati caratteri sostitutivi, che potrebbero risultare in un aspetto diverso da quello previsto.

Problemi di leggibilità: i caratteri sostitutivi utilizzati potrebbero non essere leggibili come i caratteri originali, il che potrebbe influire sulla leggibilità del documento.