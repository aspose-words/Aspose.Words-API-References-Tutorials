---
title: Configurazione del collegamento al contenuto
linktitle: Configurazione del collegamento al contenuto
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per impostare il collegamento al contenuto in un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-properties/configuring-link-to-content/
---

In questo tutorial ti guideremo attraverso il codice sorgente C# per impostare il collegamento al contenuto con Aspose.Words per .NET. Questa funzionalità consente di collegarsi a contenuti specifici in un documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati che nel tuo progetto venga fatto riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento e del costruttore

In questo passaggio creeremo un nuovo documento e inizializzeremo il costruttore. Utilizza il seguente codice:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: crea un segnalibro

Ora creeremo un segnalibro nel documento. Utilizza il codice seguente per creare un segnalibro con testo all'interno:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Questo codice crea un segnalibro chiamato "MyBookmark" e aggiunge del testo al suo interno.

## Passaggio 4: impostazione del collegamento al contenuto

Ora configureremo il collegamento al contenuto utilizzando le proprietà del documento. Utilizzare il codice seguente per aggiungere e recuperare il collegamento al contenuto:

```csharp
// Ottieni l'elenco di tutte le proprietà personalizzate nel documento.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Aggiungi una proprietà associata al contenuto.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Questo codice aggiunge una proprietà relativa al contenuto denominata "Segnalibro" con il segnalibro "MyBookmark". Quindi, recupera informazioni sulle proprietà relative al contenuto come lo stato del collegamento, l'origine del collegamento e il valore della proprietà.

### Codice sorgente di esempio per la configurazione del collegamento al contenuto utilizzando Aspose.Words per .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Recupera un elenco di tutte le proprietà del documento personalizzato dal file.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Aggiungi la proprietà collegata al contenuto.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Ora hai imparato come configurare il collegamento al contenuto in un documento utilizzando Aspose.Words per .NET. Seguendo la guida passo passo fornita in questo tutorial, puoi creare e configurare facilmente collegamenti a contenuti specifici nei tuoi documenti.