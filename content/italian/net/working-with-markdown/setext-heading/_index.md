---
title: Intestazione Setex
linktitle: Intestazione Setex
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare le intestazioni Setext per formattare i tuoi documenti con Aspose.Words per .NET Guida passo passo.
type: docs
weight: 10
url: /it/net/working-with-markdown/setext-heading/
---

In questo tutorial ti spiegheremo come utilizzare la funzionalità Intestazione Setext con Aspose.Words per .NET. L'intestazione Setext è un metodo alternativo per formattare i titoli nei documenti Markdown.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: utilizzare lo stile di intestazione Setext

Utilizzeremo lo stile di paragrafo predefinito "Intestazione 1" per creare un'intestazione di livello 1 nel nostro documento.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Passaggio 3: reimpostazione degli stili

Ripristiniamo gli stili dei caratteri applicati in precedenza per evitare qualsiasi combinazione indesiderata di stili tra i paragrafi.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Passaggio 4: personalizzazione dei livelli di intestazione Setext

Possiamo personalizzare i livelli di intestazione di Setext aggiungendo nuovi stili di paragrafo basati su stili di intestazione esistenti. In questo esempio, stiamo creando uno stile "SetextHeading1" basato sullo stile "Intestazione 1" per rappresentare un'intestazione di livello 1 nel formato Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Passaggio 5: salvataggio del documento

Infine, possiamo salvare il documento nel formato desiderato.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Codice sorgente di esempio per titoli Setext con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utilizza un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Reimposta gli stili del paragrafo precedente per non combinare gli stili tra i paragrafi.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Reimposta gli stili del paragrafo precedente per non combinare gli stili tra i paragrafi.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Il livello di intestazione Setex verrà reimpostato su 2 se il paragrafo base ha un livello di intestazione maggiore di 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### Domande frequenti

#### D: Cos'è un'intestazione Setext Markdown?

R: Un'intestazione Setext Markdown è un modo alternativo per creare intestazioni in un documento Markdown. Utilizza caratteri di sottolineatura (= o -) per indicare diversi livelli di intestazioni.

#### D: Come utilizzare le intestazioni Setext Markdown?

R: Per utilizzare le intestazioni Setext Markdown, posiziona i caratteri di sottolineatura sotto il testo del titolo. Utilizza i segni uguali (=) per un'intestazione di livello 1 e i trattini (-) per un'intestazione di livello 2.

#### D: Esistono limitazioni nell'utilizzo delle intestazioni Setext Markdown?

R: I titoli Setext Markdown hanno limitazioni in termini di gerarchia dei titoli e non sono visivamente distinti come i titoli Markdown standard.

#### D: Posso personalizzare l'aspetto delle intestazioni Setext Markdown?

R: Nel Markdown standard, non è possibile personalizzare l'aspetto delle intestazioni Setext Markdown. Hanno un aspetto predefinito in base ai caratteri di sottolineatura utilizzati.

#### D: Le intestazioni Setext Markdown sono supportate da tutti gli editor Markdown?

R: Il supporto per le intestazioni Setext Markdown può variare a seconda degli editor Markdown. Controlla la documentazione specifica del tuo editore per essere sicuro.