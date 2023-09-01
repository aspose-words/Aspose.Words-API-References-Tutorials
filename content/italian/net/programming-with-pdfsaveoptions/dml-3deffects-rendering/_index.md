---
title: Rendering di effetti 3D 3D DML in un documento PDF
linktitle: Rendering di effetti 3D 3D DML in un documento PDF
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come abilitare il rendering degli effetti DML 3D durante la conversione in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

In questo tutorial, ti guideremo attraverso i passaggi per abilitare il rendering dell'effetto 3D DML durante la conversione in PDF con Aspose.Words per .NET. Ciò mantiene gli effetti 3D nel documento PDF generato. Seguire i passaggi seguenti:

## Passaggio 1: caricamento del documento

Inizia caricando il documento che desideri convertire in PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Assicurati di specificare il percorso corretto del documento.

## Passaggio 2: configura le opzioni di salvataggio del PDF

Crea un'istanza della classe PdfSaveOptions e abilita il rendering avanzato degli effetti DML 3D:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Questa opzione mantiene gli effetti 3D nel documento PDF generato.

## Passaggio 3: converti il documento in PDF

 Usa il`Save` metodo per convertire il documento in PDF specificando le opzioni di salvataggio:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Codice sorgente di esempio per il rendering Dml 3DEffects utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Seguendo questi passaggi, puoi facilmente abilitare il rendering degli effetti DML 3D durante la conversione in PDF con Aspose.Words per .NET.

## Conclusione

In questo tutorial, abbiamo spiegato come abilitare il rendering degli effetti DML 3D durante la conversione in PDF con Aspose.Words per .NET. Seguendo i passaggi descritti, puoi facilmente mantenere gli effetti 3D nel documento PDF generato. Utilizza questa funzione per preservare gli importanti effetti visivi del tuo documento originale.


### Domande frequenti

#### D: Cos'è il rendering degli effetti DML 3D in un documento PDF?
R: Il rendering degli effetti 3D DML in un documento PDF si riferisce alla capacità di conservare gli effetti 3D durante la conversione di un documento in formato PDF. Ciò preserva gli effetti visivi e garantisce che il documento PDF generato assomigli al documento originale.

#### D: Come posso abilitare il rendering degli effetti DML 3D durante la conversione in PDF con Aspose.Words per .NET?
R: Per abilitare il rendering degli effetti DML 3D durante la conversione in PDF con Aspose.Words per .NET, attenersi alla seguente procedura:

 Crea un'istanza di`Document` classe specificando il percorso del documento Word.

 Crea un'istanza di`PdfSaveOptions` classe e impostare il file`Dml3DEffectsRenderingMode` proprietà a`Dml3DEffectsRenderingMode.Advanced` per abilitare il rendering avanzato degli effetti DML 3D.

 Usa il`Save` metodo del`Document`classe per salvare il documento in formato PDF specificando le opzioni di salvataggio.

#### D: Come posso verificare se è stato eseguito il rendering degli effetti DML 3D nel documento PDF generato?
R: Per verificare se è stato eseguito il rendering degli effetti DML 3D nel documento PDF generato, aprire il file PDF con un visualizzatore PDF compatibile, come Adobe Acrobat Reader, ed esaminare il documento. Dovresti vedere gli effetti 3D come appaiono nel documento originale.



