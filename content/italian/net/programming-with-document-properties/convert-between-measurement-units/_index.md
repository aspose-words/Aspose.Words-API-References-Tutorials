---
title: Conversione tra unità di misura
linktitle: Conversione tra unità di misura
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata alla conversione tra unità di misura in un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-properties/convert-between-measurement-units/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per convertire tra unità di misura con Aspose.Words per .NET. Questa funzione consente di specificare margini, distanze di intestazione e piè di pagina, ecc. in diverse unità di misura.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento e del costruttore

In questo passaggio creeremo un nuovo documento e inizializzeremo il costruttore. Usa il seguente codice:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: configurare le unità di misura

Ora convertiremo i valori per i margini, le distanze di intestazione e piè di pagina, ecc. in diverse unità di misura. Utilizzare il seguente codice per specificare i valori in unità di misura specifiche:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Questo codice utilizza il`ConvertUtil` class di Aspose.Words per convertire i valori specificati in pollici (`InchToPoint` ). Puoi anche utilizzare altri metodi di conversione disponibili nel file`ConvertUtil` class per convertire i valori in altre unità di misura.

### Esempio di codice sorgente per Converti tra unità di misura utilizzando Aspose.Words per .NET

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

Ora hai imparato come eseguire la conversione tra unità di misura quando specifichi margini, distanze di intestazione e piè di pagina, ecc. in un documento utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi facilmente specificare i valori nelle unità di misura desiderate nei tuoi documenti.