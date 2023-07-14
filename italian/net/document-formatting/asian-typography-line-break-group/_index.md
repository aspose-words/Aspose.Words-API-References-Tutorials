---
title: Gruppo di interruzioni di riga di tipografia asiatica
linktitle: Gruppo di interruzioni di riga di tipografia asiatica
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come utilizzare il gruppo di interruzioni di riga di tipografia asiatica con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-formatting/asian-typography-line-break-group/
---

In questo tutorial, ti mostreremo come utilizzare la funzionalità di gruppo di interruzioni di riga di tipografia asiatica con Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche alla formattazione.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory per i tuoi documenti e carica il documento contenente la tipografia asiatica in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Passaggio 2: configurazione della tipografia asiatica

Ora configureremo le impostazioni tipografiche asiatiche per il primo paragrafo del documento. Ecco come:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Passaggio 3: salvare il documento

 Dopo aver inserito il campo del modulo di immissione del testo, salvare il documento nella posizione desiderata utilizzando il file`Save` metodo. Assicurati di fornire il percorso file appropriato:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Codice sorgente di esempio per Asian Typography Line Break Group utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Asian Typography Line Break Group con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Con questo codice sarai in grado di applicare il gruppo di interruzioni di riga di tipografia asiatica utilizzando Aspose.Words per .NET.

