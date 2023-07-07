---
title: Intestazione Setext
linktitle: Intestazione Setext
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare le intestazioni Setext per formattare i tuoi documenti con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/setext-heading/
---

In questo tutorial, ti illustreremo come utilizzare la funzione Setext Heading con Aspose.Words per .NET. Setext Heading è un metodo alternativo per formattare i titoli nei documenti Markdown.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: utilizzo dello stile di intestazione Setext

Useremo lo stile di paragrafo predefinito "Intestazione 1" per creare un'intestazione di livello 1 nel nostro documento.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Passaggio 3: ripristino degli stili

Ripristiniamo gli stili di carattere applicati in precedenza per evitare qualsiasi combinazione indesiderata di stili tra i paragrafi.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Passaggio 4: personalizzazione dei livelli di intestazione Setext

Possiamo personalizzare i livelli di intestazione Setext aggiungendo nuovi stili di paragrafo basati sugli stili di intestazione esistenti. In questo esempio, stiamo creando uno stile "SetextHeading1" basato sullo stile "Heading 1" per rappresentare un'intestazione di livello 1 nel formato Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Passaggio 5: salvare il documento

Infine, possiamo salvare il documento nel formato desiderato.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Esempio di codice sorgente per titoli Setext con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Ripristina gli stili del paragrafo precedente per non combinare gli stili tra i paragrafi.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Ripristina gli stili del paragrafo precedente per non combinare gli stili tra i paragrafi.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Il livello di intestazione Setex verrà reimpostato su 2 se il paragrafo di base ha un livello di intestazione maggiore di 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### FAQ

#### D: Cos'è un'intestazione Setext Markdown?

R: Un'intestazione Setext Markdown è un modo alternativo per creare intestazioni in un documento Markdown. Utilizza caratteri di sottolineatura (= o -) per indicare diversi livelli di intestazioni.

#### D: Come utilizzare le intestazioni Setext Markdown?

R: Per utilizzare i titoli Setext Markdown, posiziona i caratteri di sottolineatura sotto il testo del titolo. Utilizza i segni di uguale (=) per un'intestazione di livello 1 e i trattini (-) per un'intestazione di livello 2.

#### D: Ci sono limitazioni nell'uso delle intestazioni Setext Markdown?

R: Le intestazioni Setext Markdown hanno limitazioni in termini di gerarchia delle intestazioni e non sono visivamente distinte come le intestazioni Markdown standard.

#### D: Posso personalizzare l'aspetto delle intestazioni di Setext Markdown?

R: In Markdown standard, non è possibile personalizzare l'aspetto delle intestazioni Setext Markdown. Hanno un aspetto predefinito basato sui caratteri di sottolineatura utilizzati.

#### D: Le intestazioni Setext Markdown sono supportate da tutti gli editor Markdown?

R: Il supporto per le intestazioni Setext Markdown può variare tra gli editor Markdown. Controlla la documentazione specifica del tuo editore per esserne sicuro.