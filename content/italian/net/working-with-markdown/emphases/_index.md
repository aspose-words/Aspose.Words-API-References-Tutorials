---
title: Enfasi
linktitle: Enfasi
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come utilizzare le sottolineature (grassetto e corsivo) con Aspose.Words per la guida passo-passo .NET.
type: docs
weight: 10
url: /it/net/working-with-markdown/emphases/
---

In questo esempio, spiegheremo come utilizzare le sottolineature con Aspose.Words per .NET. l'enfasi viene utilizzata per enfatizzare alcune parti del testo, come il grassetto e il corsivo.

## Passaggio 1: inizializzazione del documento

 Innanzitutto, inizializzeremo il documento creando un'istanza di`Document` classe.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Passaggio 2: utilizzo di un generatore di documenti

Successivamente, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: aggiungi testo con Enfasi

Possiamo aggiungere testo di enfasi modificando le proprietà del carattere del generatore di documenti. In questo esempio, usiamo il grassetto e il corsivo per enfatizzare diverse parti del testo.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Passaggio 4: salvare il documento

 Infine, possiamo salvare il documento nel formato desiderato. In questo esempio, stiamo usando il`.md` estensione per un formato Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Congratulazioni! Ora hai imparato come utilizzare le sottolineature con Aspose.Words per .NET.

### Esempio di codice sorgente per Emphases utilizzando Aspose.Words per .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### FAQ

#### D: Come faccio a evidenziare il testo usando Markdown?

R: Per evidenziare il testo utilizzando Markdown, racchiudi semplicemente il testo con i simboli appropriati. Utilizzo`*` O`_` per il corsivo,`**` O`__` per grassetto, e`~~` per barrato.

#### D: Possiamo combinare punti salienti diversi nello stesso testo?

 R: Sì, è possibile combinare diverse evidenziazioni nello stesso testo. Ad esempio, puoi mettere in grassetto e in corsivo una parola utilizzando entrambi`**` E`*` intorno alla parola.

#### D: Quali opzioni di evidenziazione sono disponibili in Markdown?

R: Le opzioni di evidenziazione disponibili in Markdown sono in corsivo (`*` O`_`), grassetto (`**` O`__`) e barrato (`~~`).

#### D: Come gestisco i casi in cui il testo contiene caratteri speciali utilizzati da Markdown per l'evidenziazione?

 R: Se il testo contiene caratteri speciali utilizzati da Markdown per l'evidenziazione, puoi eseguirne l'escape facendoli precedere da a`\` . Per esempio,`\*` visualizzerà un asterisco letterale.

#### D: Possiamo personalizzare l'aspetto dell'evidenziazione usando i CSS?

R: L'evidenziazione in Markdown viene solitamente resa utilizzando gli stili predefiniti del browser. Se converti il tuo Markdown in HTML, puoi personalizzare l'aspetto dell'evidenziazione utilizzando le regole CSS.