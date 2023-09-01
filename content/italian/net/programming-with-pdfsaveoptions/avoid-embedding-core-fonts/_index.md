---
title: Riduci le dimensioni del file PDF non incorporando i caratteri principali
linktitle: Riduci le dimensioni del file PDF non incorporando i caratteri principali
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come ridurre le dimensioni del file PDF non incorporando i caratteri principali durante la conversione di documenti Word in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

In questo tutorial, ti guideremo attraverso i passaggi su come ridurre le dimensioni del file PDF non incorporando i caratteri principali con Aspose.Words per .NET. Questa funzione consente di controllare se i caratteri di base come Arial, Times New Roman, ecc. devono essere incorporati nel PDF durante la conversione di un documento Word. Seguire i passaggi seguenti:

## Passaggio 1: caricamento del documento

Inizia caricando il documento Word che desideri convertire in PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assicurati di specificare il percorso corretto del tuo documento Word.

## Passaggio 2: imposta le opzioni di conversione PDF

Crea un'istanza della classe PdfSaveOptions e abilita l'elusione dell'incorporamento dei caratteri di base:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Questa opzione controlla se i caratteri di base devono essere incorporati o meno nel PDF.

## Passaggio 3: converti il documento in PDF

 Usa il`Save` metodo per convertire il documento Word in PDF specificando le opzioni di conversione:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Codice sorgente di esempio per evitare di incorporare caratteri principali utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per utilizzare la funzionalità per evitare l'incorporamento dei caratteri principali con Aspose.Words per .NET:

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

In questo tutorial, abbiamo spiegato come ridurre le dimensioni di un file PDF non incorporando caratteri di base con Aspose.Words per .NET. Questa funzionalità ti consente di controllare se i caratteri di base devono essere incorporati nel PDF durante la conversione di un documento Word. Seguendo i passaggi descritti, puoi controllare facilmente l'incorporamento o il non incorporamento dei caratteri di base, il che può aiutare a ridurre le dimensioni del file PDF e garantire una migliore compatibilità e un aspetto coerente del documento su diversi dispositivi e piattaforme. Non dimenticare di considerare le conseguenze della mancata incorporazione dei caratteri di base e di sperimentare per garantire che il documento venga visualizzato come previsto.

### Domande frequenti

#### D: Qual è l'opzione per non incorporare i caratteri di base in un file PDF e perché è importante?
R: L'opzione per non incorporare i caratteri di base in un file PDF controlla se i caratteri di base come Arial, Times New Roman, ecc. devono essere incorporati nel PDF durante la conversione di un documento Word. Questo può essere importante per ridurre la dimensione del file PDF evitando di includere caratteri comunemente disponibili sui sistemi di lettura PDF. Può anche contribuire a garantire una migliore compatibilità e un aspetto coerente del documento PDF su diversi dispositivi e piattaforme.

#### D: Come posso configurare Aspose.Words per .NET per non incorporare i caratteri di base in un file PDF?
R: Per configurare Aspose.Words per .NET per non incorporare i caratteri principali in un file PDF, attenersi alla seguente procedura:

 Imposta il percorso della directory in cui si trovano i tuoi documenti sostituendo`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory dei documenti.

 Carica il documento Word che desideri convertire in PDF utilizzando il file`Document` classe e il percorso del documento specificato.

 Crea un'istanza di`PdfSaveOptions` classe e impostare il file`UseCoreFonts` proprietà a`true`. Ciò eviterà l'incorporamento dei caratteri di base nel file PDF generato.

 Usa il`Save` metodo del`Document` oggetto per salvare il documento in formato PDF specificando le opzioni di conversione configurate in precedenza.

#### D: Quali sono i vantaggi di non incorporare i caratteri di base in un file PDF?
R: I vantaggi di non incorporare i caratteri di base in un file PDF sono:

Riduzione delle dimensioni del file PDF: evitando di incorporare caratteri comunemente disponibili come Arial, Times New Roman, ecc., è possibile ridurre le dimensioni del file PDF, semplificando l'archiviazione, la condivisione e il trasferimento dei file.

Migliore compatibilità: utilizzando i caratteri di base comunemente disponibili sui sistemi di lettura PDF, garantisci una migliore compatibilità e aspetto del documento su diversi dispositivi e piattaforme.

#### D: Quali sono le conseguenze se non si incorporano i caratteri di base in un file PDF?
R: Le conseguenze della mancata incorporazione dei caratteri di base in un file PDF sono le seguenti:

Aspetto diverso: se i caratteri di base non sono disponibili nel sistema in cui viene aperto il PDF, verranno utilizzati caratteri sostitutivi, il che potrebbe comportare un aspetto diverso da quello previsto.

Problemi di leggibilità: i caratteri sostitutivi utilizzati potrebbero non essere leggibili come i caratteri originali, il che potrebbe influire sulla leggibilità del documento.