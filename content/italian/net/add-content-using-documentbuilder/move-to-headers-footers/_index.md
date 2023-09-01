---
title: Passa ai piè di pagina delle intestazioni nel documento di Word
linktitle: Passa ai piè di pagina delle intestazioni nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare Aspose.Words per .NET per navigare e modificare intestazioni e piè di pagina nei documenti di Word con questa guida passo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/move-to-headers-footers/
---
In questo esempio, esploreremo la funzionalità Move To Headers Footers di Aspose.Words per .NET. Aspose.Words è una potente libreria di manipolazione di documenti che consente agli sviluppatori di creare, modificare e convertire documenti Word a livello di codice. La funzione Sposta in intestazioni/piè di pagina ci consente di navigare tra intestazioni e piè di pagina diversi all'interno di un documento e aggiungervi contenuto.

Esaminiamo passo dopo passo il codice sorgente per capire come utilizzare la funzionalità Sposta in intestazioni/piè di pagina utilizzando Aspose.Words per .NET.

## Passaggio 1: inizializzazione del documento e del generatore di documenti

Innanzitutto, inizializza gli oggetti Document e DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: configurazione di intestazioni e piè di pagina

Specificare le impostazioni di intestazione/piè di pagina per il documento. In questo esempio, impostiamo intestazioni e piè di pagina in modo che siano diversi per la prima pagina e per le pagine pari/dispari:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Passaggio 3: creazione di intestazioni per pagine diverse

Passa a ciascun tipo di intestazione e aggiungi contenuto. In questo esempio creiamo intestazioni per la prima pagina, anche per le pagine e per tutte le altre pagine:

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
## Passaggio 5: salvataggio del documento

Salva il documento modificato nella posizione desiderata:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Assicurati di specificare il percorso e il formato del file appropriati (ad esempio, DOCX).

### Codice sorgente di esempio per Sposta in intestazioni/piè di pagina utilizzando Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Specificare che vogliamo intestazioni e piè di pagina diversi per le prime pagine, pari e dispari.
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

## Conclusione

In questo esempio, abbiamo esplorato la funzionalità Sposta in intestazioni/piè di pagina di Aspose.Words per .NET. Abbiamo imparato come navigare tra intestazioni e piè di pagina diversi all'interno di un documento Word e aggiungervi contenuto utilizzando la classe DocumentBuilder. Questa funzionalità consente agli sviluppatori di personalizzare intestazioni e piè di pagina per pagine o sezioni specifiche, offrendo flessibilità nella creazione di documenti professionali e strutturati. Aspose.Words per .NET fornisce un potente set di strumenti per manipolare a livello di codice i documenti Word, rendendolo una libreria essenziale per le applicazioni di elaborazione dei documenti.

### Domande frequenti sullo spostamento nelle intestazioni dei piè di pagina nel documento Word

#### D: Qual è lo scopo della funzionalità Sposta in intestazioni/piè di pagina in Aspose.Words per .NET?

R: La funzionalità Sposta in intestazioni/piè di pagina in Aspose.Words per .NET consente agli sviluppatori di spostarsi tra intestazioni e piè di pagina diversi all'interno di un documento Word e aggiungere contenuto ad essi a livello di codice. È utile quando è necessario personalizzare intestazioni e piè di pagina per diverse pagine o sezioni del documento.

#### D: Posso avere intestazioni e piè di pagina diversi per le diverse pagine del documento?

R: Sì, puoi specificare intestazioni e piè di pagina diversi per la prima pagina, le pagine pari e le pagine dispari utilizzando rispettivamente le proprietà PageSetup.DifferentFirstPageHeaderFooter e PageSetup.OddAndEvenPagesHeaderFooter.

#### D: Come posso aggiungere contenuto a intestazioni e piè di pagina specifici?

R: Per aggiungere contenuto a intestazioni e piè di pagina specifici, utilizzare il metodo MoveToHeaderFooter della classe DocumentBuilder. Puoi passare alle intestazioni HeaderFirst, HeaderEven e HeaderPrimary o ai piè di pagina FooterFirst, FooterEven e FooterPrimary in base alle tue esigenze.

#### D: Posso creare intestazioni e piè di pagina per una sezione specifica del documento?

R: Sì, puoi utilizzare il metodo MoveToSection della classe DocumentBuilder per spostarti in una sezione specifica del documento e quindi creare intestazioni e piè di pagina all'interno di quella sezione.

#### D: Come posso salvare il documento modificato in un file utilizzando Aspose.Words per .NET?

R: Puoi salvare il documento modificato nella posizione e nel formato desiderati utilizzando il metodo Save della classe Document. Assicurati di specificare il percorso e il formato file appropriati (ad esempio DOCX).