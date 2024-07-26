---
title: Aggiungi filigrana di testo con opzioni specifiche
linktitle: Aggiungi filigrana di testo con opzioni specifiche
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere una filigrana di testo con opzioni specifiche utilizzando Aspose.Words per .NET. Guida passo passo.
type: docs
weight: 10
url: /it/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

In questo tutorial ti spiegheremo come aggiungere una filigrana di testo con opzioni specifiche utilizzando Aspose.Words per .NET. Una filigrana di testo è un testo sovrapposto a un documento per indicare che si tratta di una bozza, di un documento riservato, ecc.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricamento del documento

Caricheremo un documento esistente utilizzando il percorso del documento.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Passaggio 3: aggiungi una filigrana di testo con opzioni specifiche

 Creeremo un'istanza del file`TextWatermarkOptions` classe e impostare le opzioni desiderate per la filigrana del testo.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Passaggio 4: salva il documento

Infine, possiamo salvare il documento con la filigrana di testo aggiunta.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Esempio di codice sorgente per l'aggiunta di filigrana di testo con opzioni specifiche con Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Congratulazioni! Ora hai imparato come aggiungere una filigrana di testo con opzioni specifiche utilizzando Aspose.Words per .NET.

