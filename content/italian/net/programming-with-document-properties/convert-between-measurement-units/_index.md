---
title: Converti tra unità di misura
linktitle: Converti tra unità di misura
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo alla conversione tra unità di misura in un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-properties/convert-between-measurement-units/
---

In questo tutorial ti guideremo attraverso il codice sorgente C# per convertire tra unità di misura con Aspose.Words per .NET. Questa funzionalità consente di specificare i margini, le distanze di intestazione e piè di pagina, ecc. in diverse unità di misura.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati che nel tuo progetto venga fatto riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento e del costruttore

In questo passaggio creeremo un nuovo documento e inizializzeremo il costruttore. Utilizza il seguente codice:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: configurare le unità di misura

Ora convertiremo i valori dei margini, delle distanze di intestazione e piè di pagina, ecc. in diverse unità di misura. Utilizzare il codice seguente per specificare i valori in unità di misura specifiche:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Questo codice utilizza il`ConvertUtil` classe di Aspose.Words per convertire i valori specificati in pollici (`InchToPoint`). Puoi anche utilizzare altri metodi di conversione disponibili nel file`ConvertUtil` classe per convertire i valori in altre unità di misura.

### Codice sorgente di esempio per convertire tra unità di misura utilizzando Aspose.Words per .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Ora hai imparato come convertire tra unità di misura quando si specificano margini, distanze di intestazione e piè di pagina, ecc. In un documento utilizzando Aspose.Words per .NET. Seguendo la guida passo passo fornita in questo tutorial, puoi facilmente specificare i valori nelle unità di misura desiderate nei tuoi documenti.