---
title: Sposta in intestazioni piè di pagina
linktitle: Sposta in intestazioni piè di pagina
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare Aspose.Words per .NET per navigare e modificare intestazioni e piè di pagina nei documenti di Word con questa guida dettagliata.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/move-to-headers-footers/
---

In questo esempio, esploreremo la funzione Move To Headers Footers di Aspose.Words per .NET. Aspose.Words è una potente libreria di manipolazione dei documenti che consente agli sviluppatori di creare, modificare e convertire i documenti di Word a livello di codice. La funzione Sposta in intestazioni/piè di pagina ci consente di navigare tra diverse intestazioni e piè di pagina all'interno di un documento e di aggiungervi contenuto.

Esaminiamo il codice sorgente passo dopo passo per capire come utilizzare la funzione Sposta in intestazioni/piè di pagina utilizzando Aspose.Words per .NET.



## Passaggio 1: inizializzazione del documento e del generatore di documenti

Innanzitutto, inizializza gli oggetti Document e DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: configurazione di intestazioni e piè di pagina

Specificare le impostazioni di intestazione/piè di pagina per il documento. In questo esempio, impostiamo intestazioni e piè di pagina diversi per la prima pagina e per le pagine pari/dispari:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Passaggio 3: creazione di intestazioni per pagine diverse

Spostati su ciascun tipo di intestazione e aggiungi contenuto. In questo esempio, creiamo intestazioni per la prima pagina, le pagine pari e tutte le altre pagine:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Passaggio 4: creazione di pagine nel documento
Aggiungi contenuto al documento per creare più pagine. Per esempio:

```csharp
// Crea due pagine nel documento.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Passaggio 5: salvare il documento

Salva il documento modificato nella posizione desiderata:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Assicurati di specificare il percorso e il formato file appropriati (ad es. DOCX).

### Esempio di codice sorgente per Sposta in intestazioni/piè di pagina utilizzando Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Specificare che vogliamo intestazioni e piè di pagina diversi per la prima pagina, pari e dispari.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Crea le intestazioni.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Crea due pagine nel documento.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```
