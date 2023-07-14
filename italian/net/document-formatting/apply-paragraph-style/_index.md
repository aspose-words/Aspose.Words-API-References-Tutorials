---
title: Applica lo stile di paragrafo
linktitle: Applica lo stile di paragrafo
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come applicare uno stile di paragrafo utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/apply-paragraph-style/
---

In questo tutorial, ti illustreremo come applicare uno stile di paragrafo usando Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare lo stile di paragrafo.

## Passaggio 1: creazione e configurazione del documento

Per iniziare, crea un nuovo documento e un oggetto DocumentBuilder associato. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: configurazione dello stile di paragrafo

Ora configureremo lo stile di paragrafo usando l'identificatore di stile incorporato. Ecco come:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## Passaggio 3: aggiungi contenuto

Stiamo per aggiungere contenuto al paragrafo. Ecco come:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### Codice sorgente di esempio per Applicare lo stile di paragrafo utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Applica stile paragrafo con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

Con questo codice sarai in grado di applicare uno stile di paragrafo usando Aspose.Words per .NET.

