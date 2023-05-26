---
title: Esportazione di proprietà personalizzate
linktitle: Esportazione di proprietà personalizzate
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come esportare proprietà personalizzate durante la conversione di documenti in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/custom-properties-export/
---

In questo tutorial, ti guideremo attraverso i passaggi per esportare le proprietà personalizzate di un documento utilizzando Aspose.Words per .NET. L'esportazione delle proprietà personalizzate consente di includere informazioni aggiuntive nel documento PDF generato. Segui i passaggi seguenti:

## Passaggio 1: creazione di un documento e aggiunta di proprietà personalizzate

Inizia creando un'istanza della classe Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Passaggio 2: aggiungi proprietà personalizzate
Successivamente, aggiungi le proprietà personalizzate desiderate. Ad esempio, per aggiungere una proprietà "Company" con il valore "Aspose", utilizzare the`Add` metodo della raccolta CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

È possibile aggiungere tutte le proprietà personalizzate necessarie.

## Passaggio 3: imposta le opzioni di esportazione PDF

Crea un'istanza della classe PdfSaveOptions e specifica come esportare le proprietà personalizzate:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Questa opzione controlla l'esportazione delle proprietà personalizzate durante la conversione in PDF.

## Passo 4: Converti documento in PDF

 Usa il`Save` metodo per convertire il documento in PDF specificando le opzioni di conversione:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Assicurati di specificare il percorso corretto per salvare il PDF convertito.

### Codice sorgente di esempio per l'esportazione di proprietà personalizzate utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per esportare proprietà personalizzate da un documento utilizzando Aspose.Words per .NET:


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Seguendo questi passaggi, puoi esportare facilmente le proprietà personalizzate di un documento durante la conversione in PDF con Aspose.Words per .NET.

