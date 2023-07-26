---
title: Riduci le dimensioni del PDF disabilitando i caratteri incorporati
linktitle: Riduci le dimensioni del PDF disabilitando i caratteri incorporati
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come ridurre le dimensioni del PDF disabilitando l'incorporamento dei caratteri di Windows durante la conversione di documenti in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

In questo tutorial, ti guideremo attraverso i passaggi per ridurre le dimensioni del PDF disabilitando l'incorporamento dei caratteri di Windows in un documento PDF con Aspose.Words per .NET. Disabilitando l'incorporamento dei caratteri, puoi ridurre le dimensioni del file PDF generato. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento

Inizia caricando il documento che desideri convertire in PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assicurati di specificare il percorso corretto del documento.

## Passaggio 2: imposta le opzioni di salvataggio del PDF

Crea un'istanza della classe PdfSaveOptions e specifica come incorporare i font:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Questa opzione consente di disattivare l'integrazione dei font Windows nel file PDF generato.

## Passo 3: Converti documento in PDF

 Usa il`Save` metodo per convertire il documento in PDF specificando le opzioni di conversione:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Codice sorgente di esempio per disabilitare i caratteri incorporati di Windows utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per disabilitare l'incorporamento dei font Windows in un documento PDF con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Il PDF di output verrà salvato senza incorporare i caratteri Windows standard.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Seguendo questi passaggi, puoi facilmente disabilitare l'incorporamento dei caratteri Windows in un documento PDF con Aspose.Words per .NET.


## Conclusione

In questo tutorial, abbiamo imparato come ridurre le dimensioni di un file PDF disabilitando l'incorporamento dei caratteri di Windows utilizzando Aspose.Words per .NET. Disattivando l'incorporamento dei caratteri, è possibile ridurre le dimensioni del file PDF generato, semplificando l'archiviazione, la condivisione e il trasferimento dei file. Tuttavia, è importante notare che la disattivazione dell'incorporamento dei caratteri di Windows può causare modifiche all'aspetto e alla formattazione del documento PDF finale. Assicurati di considerare queste conseguenze quando usi questa funzione. Sentiti libero di esplorare più funzionalità di Aspose.Words per .NET per ottimizzare la generazione dei tuoi file PDF.

### Domande frequenti

#### D: Cos'è la disabilitazione dell'incorporamento dei caratteri di Windows in un documento PDF e perché è importante?
R: La disabilitazione dell'incorporamento dei font Windows in un documento PDF è il processo che impedisce l'inclusione dei font Windows nel file PDF generato. Ciò riduce le dimensioni del file PDF rimuovendo i dati dei caratteri di Windows incorporati. Questo può essere importante per ridurre le dimensioni dei file PDF, che possono renderli più facili da archiviare, condividere e trasferire più velocemente.

#### D: Come posso disabilitare l'incorporamento dei caratteri di Windows in un documento PDF utilizzando Aspose.Words per .NET?
R: Per disabilitare l'incorporamento dei caratteri Windows in un documento PDF utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:

 Carica il documento che desideri convertire in PDF utilizzando il file`Document` classe e percorso del documento.

 Crea un'istanza di`PdfSaveOptions`classe e impostare il`FontEmbeddingMode` proprietà a`PdfFontEmbeddingMode.EmbedNone`. Ciò disabilita l'incorporamento dei caratteri Windows nel file PDF generato.

 Usa il`Save` metodo del`Document` oggetto per convertire il documento in PDF specificando le opzioni di conversione configurate in precedenza.

#### D: Quali sono i vantaggi della disabilitazione dell'incorporamento dei font di Windows in un documento PDF?
R: I vantaggi della disabilitazione dell'incorporamento dei caratteri di Windows in un documento PDF sono:

Dimensioni file PDF ridotte: disabilitando l'incorporamento dei caratteri Windows, i dati dei caratteri Windows incorporati vengono rimossi, riducendo le dimensioni del file PDF generato.

Archiviazione più semplice: i file PDF più piccoli sono più facili da archiviare, salvare e trasferire.

Condivisione e trasferimento più veloci: i file PDF più piccoli possono essere condivisi e trasferiti più velocemente, risparmiando tempo e risorse.

#### D: Quali sono le conseguenze della disabilitazione dell'incorporamento dei caratteri di Windows in un documento PDF?
R: La disabilitazione dell'incorporamento dei font Windows in un documento PDF può portare a conseguenze quali:

Perdita dell'aspetto e della formattazione: se i caratteri Windows specificati nel documento non sono disponibili sul sistema in cui viene aperto il PDF, verranno utilizzati caratteri sostitutivi, che potrebbero causare un aspetto e una formattazione errati. forma diversa da quelle previste.

Problemi di leggibilità: se i caratteri sostitutivi utilizzati non sono leggibili come i caratteri originali, ciò potrebbe influire sulla leggibilità del testo nel documento PDF.