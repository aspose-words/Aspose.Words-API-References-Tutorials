---
title: Pagina per pagina
linktitle: Pagina per pagina
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per spiegare il codice sorgente C# della funzione Aspose.Words pagina per pagina per .NET
type: docs
weight: 10
url: /it/net/split-document/page-by-page/
---

In questo tutorial, ti illustreremo come suddividere un documento Word in singole pagine utilizzando la funzione Pagina per pagina di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e ottenere documenti separati per ogni pagina.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory per il tuo documento e carica il documento in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Passaggio 2: dividere il documento per pagina

Ora itereremo attraverso ogni pagina del documento e spezzeremo il documento in singole pagine. Ecco come:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Salva ogni pagina come documento separato.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

## Passaggio 3: unisci i documenti

Una volta che hai documenti separati per ogni pagina, puoi unirli se necessario. Ecco come:

```csharp
MergeDocuments();
```

### Esempio di codice sorgente per Page By Page utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Pagina per pagina di Aspose.Words per .NET:

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
	

	MergeDocuments();

```

Con questo codice sarai in grado di dividere un documento Word in singole pagine utilizzando Aspose.Words per .NET. Puoi anche unire documenti separati, se necessario.

