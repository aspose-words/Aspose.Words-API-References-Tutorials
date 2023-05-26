---
title: Collegamento
linktitle: Collegamento
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire collegamenti con Aspose.Words per .NET. Guida passo dopo passo.
type: docs
weight: 10
url: /it/net/working-with-markdown/link/
---

In questo esempio, ti illustreremo come utilizzare la funzionalità dei collegamenti con Aspose.Words per .NET. I collegamenti vengono utilizzati per creare riferimenti cliccabili a siti Web o altri documenti.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: Inserimento di un collegamento

 Possiamo inserire un collegamento utilizzando il file`Insertlink` metodo del generatore di documenti. Dobbiamo specificare il testo del collegamento, qui "Aspose", così come l'URL di destinazione.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", falso);
```

### Codice sorgente di esempio per collegamenti con Aspose.Words per .NET


```csharp
	// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
	DocumentBuilder builder = new DocumentBuilder();

	// Inserisci collegamento.
	builder.Insertlink("Aspose", "https://www.aspose.com", falso);
            
```
Congratulazioni! Ora hai imparato come utilizzare la funzionalità dei collegamenti con Aspose.Words per .NET.

