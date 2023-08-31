---
title: Collegamento
linktitle: Collegamento
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire collegamenti con Aspose.Words per .NET. Guida passo passo.
type: docs
weight: 10
url: /it/net/working-with-markdown/link/
---

In questo esempio, ti spiegheremo come utilizzare la funzionalità dei collegamenti con Aspose.Words per .NET. I collegamenti vengono utilizzati per creare riferimenti cliccabili a siti Web o altri documenti.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: inserimento di un collegamento

 Possiamo inserire un collegamento utilizzando il file`Insertlink` metodo del generatore di documenti. Dobbiamo specificare il testo del collegamento, qui "Aspose", nonché l'URL di destinazione.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", falso);
```

### Codice sorgente di esempio per i collegamenti con Aspose.Words per .NET


```csharp
// Utilizza un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

// Inserisci collegamento.
builder.Insertlink("Aspose", "https://www.aspose.com", falso);
```
Congratulazioni! Ora hai imparato come utilizzare la funzionalità dei collegamenti con Aspose.Words per .NET.


### Domande frequenti

#### D: Come posso collegarmi a un URL in Aspose.Words?

 R: Per collegarsi a un indirizzo URL in Aspose.Words, è possibile utilizzare il file`<a>` etichetta con il`href` attributo contenente l'indirizzo URL. Ad esempio, puoi usare`<a href="https://www.aspose.com">Click Here</a>` per collegarsi all'URL "https://www.example.com" con il testo visualizzato "Fai clic qui".

#### D: È possibile collegarsi a un segnalibro interno in Aspose.Words?

 R: Sì, è possibile collegarsi a un segnalibro interno in Aspose.Words. Puoi usare il`<a>` etichetta con il`href` attributo contenente il nome del segnalibro preceduto da un hash (#). Per esempio,`<a href="#bookmark1">Go to bookmark 1</a>` si collegherà al segnalibro denominato "bookmark1" nel documento.

#### D: Come posso personalizzare il testo visualizzato di un collegamento in Aspose.Words?

R: Per personalizzare il testo visualizzato di un collegamento in Aspose.Words, è possibile modificare il contenuto tra i`<a>` tag. Per esempio,`<a href="https://www.aspose.com">Click here</a>` visualizzerà il testo "Fai clic qui" come collegamento ipertestuale.

#### D: Posso specificare una destinazione per un collegamento in Aspose.Words?

 R: Sì, puoi specificare una destinazione per un collegamento in Aspose.Words utilizzando il file`target` attributo del`<a>` etichetta. Per esempio,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` aprirà il collegamento in una nuova finestra o scheda.