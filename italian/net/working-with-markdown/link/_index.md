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


### FAQ

#### D: Come posso collegarmi a un URL in Aspose.Words?

 A: Per collegarsi a un indirizzo URL in Aspose.Words, è possibile utilizzare il file`<a>` etichetta con il`href` attributo contenente l'indirizzo URL. Ad esempio, puoi usare`<a href="https://www.aspose.com">Click Here</a>` per creare un collegamento ipertestuale all'URL "https://www.example.com " con il testo visualizzato "Fai clic qui".

#### D: È possibile collegarsi a un segnalibro interno in Aspose.Words?

 A: Sì, è possibile collegarsi a un segnalibro interno in Aspose.Words. Puoi usare il`<a>` etichetta con il`href` attributo contenente il nome del segnalibro preceduto da un cancelletto (#). Per esempio,`<a href="#bookmark1">Go to bookmark 1</a>` collegherà al segnalibro denominato "bookmark1" nel documento.

#### D: Come posso personalizzare il testo visualizzato di un collegamento in Aspose.Words?

A: Per personalizzare il testo visualizzato di un collegamento in Aspose.Words, è possibile modificare il contenuto tra il file`<a>` tag. Per esempio,`<a href="https://www.aspose.com">Click here</a>` visualizzerà il testo "Clicca qui" come collegamento ipertestuale.

#### D: Posso specificare una destinazione per un collegamento in Aspose.Words?

 A: Sì, è possibile specificare una destinazione per un collegamento in Aspose.Words utilizzando il file`target` attributo del`<a>` etichetta. Per esempio,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` aprirà il collegamento in una nuova finestra o scheda.