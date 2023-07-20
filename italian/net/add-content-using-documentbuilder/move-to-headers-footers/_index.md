---
title: Sposta nei piè di pagina delle intestazioni nel documento di Word
linktitle: Sposta nei piè di pagina delle intestazioni nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
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

//Specificare che vogliamo intestazioni e piè di pagina diversi per la prima pagina, pari e dispari.
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

In questo esempio, abbiamo esplorato la funzionalità Sposta in intestazioni/piè di pagina di Aspose.Words per .NET. Abbiamo imparato come navigare tra diverse intestazioni e piè di pagina all'interno di un documento Word e aggiungervi contenuto utilizzando la classe DocumentBuilder. Questa funzione consente agli sviluppatori di personalizzare intestazioni e piè di pagina per pagine o sezioni specifiche, fornendo flessibilità nella creazione di documenti professionali e strutturati. Aspose.Words per .NET fornisce un potente set di strumenti per la manipolazione programmatica dei documenti Word, rendendolo una libreria essenziale per le applicazioni di elaborazione dei documenti.

### Domande frequenti per passare alle intestazioni a piè di pagina nel documento di Word

#### D: Qual è lo scopo della funzione Sposta in intestazioni/piè di pagina in Aspose.Words per .NET?

R: La funzione Sposta in intestazioni/piè di pagina in Aspose.Words per .NET consente agli sviluppatori di navigare tra diverse intestazioni e piè di pagina all'interno di un documento Word e aggiungervi contenuto in modo programmatico. È utile quando è necessario personalizzare intestazioni e piè di pagina per diverse pagine o sezioni del documento.

#### D: Posso avere intestazioni e piè di pagina diversi per pagine diverse nel documento?

R: Sì, puoi specificare intestazioni e piè di pagina diversi per la prima pagina, le pagine pari e le pagine dispari utilizzando rispettivamente le proprietà PageSetup.DifferentFirstPageHeaderFooter e PageSetup.OddAndEvenPagesHeaderFooter.

#### D: Come posso aggiungere contenuti a intestazioni e piè di pagina specifici?

R: Per aggiungere contenuto a intestazioni e piè di pagina specifici, utilizzare il metodo MoveToHeaderFooter della classe DocumentBuilder. Puoi passare alle intestazioni HeaderFirst, HeaderEven e HeaderPrimary o ai piè di pagina FooterFirst, FooterEven e FooterPrimary in base alle tue esigenze.

#### D: Posso creare intestazioni e piè di pagina per una sezione specifica del documento?

R: Sì, puoi utilizzare il metodo MoveToSection della classe DocumentBuilder per passare a una sezione specifica del documento e quindi creare intestazioni e piè di pagina all'interno di tale sezione.

#### D: Come posso salvare il documento modificato in un file utilizzando Aspose.Words per .NET?

R: È possibile salvare il documento modificato nella posizione e nel formato desiderati utilizzando il metodo Save della classe Document. Assicurati di specificare il percorso file e il formato file appropriati (ad es. DOCX).