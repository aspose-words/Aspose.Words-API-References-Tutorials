---
title: Dml 3DEffects Rendering
linktitle: Dml 3DEffects Rendering
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come abilitare il rendering degli effetti DML 3D durante la conversione in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

In questo tutorial, ti guideremo attraverso i passaggi per abilitare il rendering dell'effetto DML 3D durante la conversione in PDF con Aspose.Words per .NET. Ciò mantiene gli effetti 3D nel documento PDF generato. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento

Inizia caricando il documento che desideri convertire in PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assicurati di specificare il percorso corretto del documento.

## Passaggio 2: configurare le opzioni di salvataggio PDF

Crea un'istanza della classe PdfSaveOptions e abilita il rendering avanzato degli effetti 3D DML:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Questa opzione mantiene gli effetti 3D nel documento PDF generato.

## Passo 3: Converti documento in PDF

 Usa il`Save` metodo per convertire il documento in PDF specificando le opzioni di salvataggio:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Esempio di codice sorgente per Dml 3DEffects Rendering utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Seguendo questi passaggi, puoi abilitare facilmente il rendering degli effetti DML 3D durante la conversione in PDF con Aspose.Words per .NET.



