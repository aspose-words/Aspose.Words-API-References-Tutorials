---
title: Collegamento automatico
linktitle: Collegamento automatico
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire il collegamento automatico con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/autolink/
---

In questo esempio, spiegheremo come utilizzare la funzione "Autolink" con Aspose.Words per .NET. Questa funzione consente di inserire automaticamente collegamenti ipertestuali nel documento.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: Inserimento di un collegamento ipertestuale

 Possiamo inserire un collegamento ipertestuale utilizzando il file`InsertHyperlink` metodo del generatore di documenti. Specifichiamo l'URL e il testo da visualizzare per il collegamento.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", falso);
```

## Passaggio 3: Inserimento di un indirizzo e-mail come collegamento

Possiamo anche inserire un indirizzo email come link usando il prefisso "mailto:". Ciò consentirà agli utenti di fare clic sul collegamento per aprire il client di posta predefinito.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Passaggio 4: salvare il documento

Infine, possiamo salvare il documento nel formato desiderato.

### Esempio di codice sorgente per Autolink utilizzando Aspose.Words per .NET


```csharp
	// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
	DocumentBuilder builder = new DocumentBuilder();

	//Inserisci collegamento ipertestuale.
	builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", falso);
	builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
            
```


Congratulazioni! Ora hai imparato come utilizzare la funzione "Autolink" con Aspose.Words per .NET.

