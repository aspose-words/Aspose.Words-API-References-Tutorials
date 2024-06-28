---
title: Esporta proprietà personalizzate in un documento PDF
linktitle: Esporta proprietà personalizzate in un documento PDF
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come esportare proprietà personalizzate durante la conversione di documenti in PDF con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-pdfsaveoptions/custom-properties-export/
---

In questo tutorial ti guideremo attraverso i passaggi per esportare le proprietà personalizzate di un documento in un documento PDF utilizzando Aspose.Words per .NET. L'esportazione delle proprietà personalizzate consente di includere informazioni aggiuntive nel documento PDF generato. Seguire i passaggi seguenti:

## Passaggio 1: creazione di un documento e aggiunta di proprietà personalizzate

Inizia creando un'istanza della classe Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Passaggio 2: aggiungi proprietà personalizzate
 Successivamente, aggiungi le proprietà personalizzate desiderate. Ad esempio, per aggiungere una proprietà "Azienda" con il valore "Apose", utilizzare il file`Add` metodo della raccolta CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Puoi aggiungere tutte le proprietà personalizzate necessarie.

## Passaggio 3: imposta le opzioni di esportazione PDF

Crea un'istanza della classe PdfSaveOptions e specifica come esportare le proprietà personalizzate:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Questa opzione controlla l'esportazione delle proprietà personalizzate durante la conversione in PDF.

## Passaggio 4: converti il documento in PDF

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


## Conclusione

In questo tutorial, abbiamo spiegato come esportare proprietà personalizzate da un documento in un documento PDF utilizzando Aspose.Words per .NET. Seguendo i passaggi descritti, puoi includere facilmente informazioni aggiuntive nel documento PDF generato esportando le proprietà personalizzate del documento. Sfrutta le funzionalità di Aspose.Words per .NET per personalizzare e arricchire i tuoi documenti PDF esportando proprietà personalizzate.

### Domande frequenti

#### D: Che cosa significa esportare proprietà personalizzate in un documento PDF?
R: L'esportazione delle proprietà personalizzate in un documento PDF consente di includere informazioni aggiuntive nel documento PDF generato. Le proprietà personalizzate sono metadati specifici del tuo documento, come tag, parole chiave o credenziali. Esportando queste proprietà personalizzate, puoi renderle disponibili agli utenti durante la visualizzazione del documento PDF.

#### D: Come posso esportare le proprietà personalizzate di un documento in un documento PDF utilizzando Aspose.Words per .NET?
R: Per esportare le proprietà personalizzate di un documento in un documento PDF utilizzando Aspose.Words per .NET, attenersi alla seguente procedura:

 Crea un'istanza di`Document` classe.

 Aggiungi le proprietà personalizzate desiderate utilizzando il file`CustomDocumentProperties` collezione. Ad esempio, utilizzare il`Add` metodo per aggiungere una proprietà "Azienda" con il valore "Apose".

 Crea un'istanza di`PdfSaveOptions` classe e specificare come esportare le proprietà personalizzate utilizzando il file`CustomPropertiesExport` proprietà. IL`PdfCustomPropertiesExport.Standard` value esporta le proprietà personalizzate in base alle impostazioni predefinite.

 Usa il`Save` metodo del`Document` classe per convertire il documento in PDF specificando le opzioni di conversione.

#### D: Come posso accedere alle proprietà personalizzate di un documento PDF?
R: Per accedere alle proprietà personalizzate di un documento PDF, è possibile utilizzare un lettore PDF compatibile che supporti la visualizzazione delle proprietà del documento. I lettori PDF più comuni, come Adobe Acrobat Reader, forniscono l'accesso ai metadati e alle proprietà di un documento PDF. Di solito puoi trovare queste opzioni nel menu "File" o facendo clic con il pulsante destro del mouse sul documento e selezionando "Proprietà".