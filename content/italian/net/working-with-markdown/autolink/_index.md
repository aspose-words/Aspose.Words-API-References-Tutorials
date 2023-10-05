---
title: Collegamento automatico
linktitle: Collegamento automatico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire il collegamento automatico con Aspose.Words per .NET Guida passo passo.
type: docs
weight: 10
url: /it/net/working-with-markdown/autolink/
---

In questo esempio, spiegheremo come utilizzare la funzionalità "Autolink" con Aspose.Words per .NET. Questa funzione ti consente di inserire automaticamente collegamenti ipertestuali nel tuo documento.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: inserimento di un collegamento ipertestuale

 Possiamo inserire un collegamento ipertestuale utilizzando il file`InsertHyperlink` metodo del generatore di documenti. Specifichiamo l'URL e il testo da visualizzare per il collegamento.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", falso);
```

## Passaggio 3: inserimento di un indirizzo email come collegamento

Possiamo anche inserire un indirizzo email come collegamento utilizzando il prefisso "mailto:". Ciò consentirà agli utenti di fare clic sul collegamento per aprire il client di posta elettronica predefinito.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Passaggio 4: salvataggio del documento

Infine, possiamo salvare il documento nel formato desiderato.

### Esempio di codice sorgente per il collegamento automatico utilizzando Aspose.Words per .NET


```csharp
// Utilizza un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

// Inserisci collegamento ipertestuale.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", falso);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Congratulazioni! Ora hai imparato come utilizzare la funzione "Collegamento automatico" con Aspose.Words per .NET.


### Domande frequenti

#### D: Come posso creare un collegamento automatico a un indirizzo URL in Aspose.Words?

R: Per creare un collegamento automatico a un indirizzo URL in Aspose.Words, è possibile utilizzare il file`<a>` etichetta con il`href` attributo contenente l'indirizzo URL. Ad esempio, puoi usare`<a href="https://www.aspose.com">https://www.aspose.com</a>` per collegarsi automaticamente al "https: //www.aspose.com".

#### D: È possibile personalizzare il testo visualizzato di un collegamento automatico in Aspose.Words?

 R: Sì, puoi personalizzare il testo visualizzato di un collegamento automatico in Aspose.Words. Invece di utilizzare l'indirizzo URL come testo visualizzato, puoi utilizzare qualsiasi altro testo sostituendo il contenuto tra i file`<a>` tag. Ad esempio, puoi usare`<a href="https://www.aspose.com">Click here</a>` per visualizzare il testo "Clicca qui" come collegamento automatico.

#### D: Come posso aggiungere ulteriori attributi a un collegamento automatico in Aspose.Words?

 R: Per aggiungere ulteriori attributi a un collegamento automatico in Aspose.Words, è possibile utilizzare attributi HTML aggiuntivi all'interno del file`<a>` etichetta. Ad esempio, puoi usare`<a href="https://www.aspose.com" target="_blank">Link</a>` per aprire il collegamento in una nuova finestra o scheda utilizzando il file` attribute target="_blank"`.