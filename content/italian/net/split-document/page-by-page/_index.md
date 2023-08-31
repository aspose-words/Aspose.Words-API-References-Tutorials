---
title: Dividi il documento Word per pagina
linktitle: Dividi il documento Word per pagina
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come dividere un documento Word in singole pagine utilizzando Aspose.Words per .NET. Questa potente API semplifica il processo di suddivisione dei documenti, rendendolo efficiente e conveniente.
type: docs
weight: 10
url: /it/net/split-document/page-by-page/
---

In questo tutorial ti spiegheremo come dividere un documento Word in singole pagine utilizzando la funzionalità di elaborazione dei documenti di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e ottenere documenti separati per ogni pagina.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory per il tuo documento e carica il documento in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Passaggio 2: suddivisione del documento per pagina

Ora ripeteremo ogni pagina del documento e suddivideremo il documento in singole pagine. Ecco come:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Salva ogni pagina come documento separato.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Codice sorgente di esempio per pagina per pagina utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzionalità Pagina per pagina di Aspose.Words per .NET:

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// Salva ogni pagina come documento separato.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

Con questo codice sarai in grado di dividere un documento Word in singole pagine utilizzando Aspose.Words per .NET. Se necessario, puoi anche unire documenti separati.

## Conclusione

Congratulazioni! Hai imparato come dividere un documento Word in singole pagine utilizzando la funzionalità Pagina per pagina di Aspose.Words per .NET. Seguendo il codice sorgente fornito, puoi estrarre ciascuna pagina di un documento e salvarle come documenti separati.

Dividere un documento per pagina può essere utile quando è necessario lavorare con pagine specifiche o distribuire il contenuto in modo granulare. Aspose.Words per .NET fornisce una potente API che semplifica il processo di divisione dei documenti, rendendolo efficiente e conveniente.

Sentiti libero di esplorare altre funzionalità offerte da Aspose.Words per .NET per migliorare le tue capacità di elaborazione dei documenti e semplificare il tuo flusso di lavoro.

### Domande frequenti

#### Come posso dividere un documento in più pagine utilizzando Aspose.Words per .NET?

 Per dividere un documento in più pagine, è possibile utilizzare il file`ExtractPages` metodo dell'API Aspose.Words per ottenere l'intervallo di pagine. Specificando la pagina iniziale e il numero di pagine da estrarre, è possibile creare documenti separati per ogni pagina.

#### Posso personalizzare il formato di output quando divido un documento per pagina?

Sì, Aspose.Words per .NET supporta vari formati di output quando si divide un documento per pagina. Puoi salvare ogni pagina come documento separato in formati come DOCX, PDF, HTML e altri, a seconda delle tue esigenze.

#### Posso dividere un documento in base a un intervallo di pagine specifico?

Assolutamente! Aspose.Words per .NET ti consente di dividere un documento in base a un intervallo di pagine specifico. Regolando la pagina iniziale e il numero di pagine da estrarre, puoi definire con precisione l'intervallo di pagine per dividere il documento.

#### È possibile unire nuovamente i documenti divisi in un unico documento?

Sì, puoi unire nuovamente i documenti divisi in un unico documento utilizzando la funzionalità di unione fornita da Aspose.Words per .NET. Combinando i documenti separati, puoi ricreare il documento originale o crearne uno nuovo con una struttura diversa, a seconda delle necessità.