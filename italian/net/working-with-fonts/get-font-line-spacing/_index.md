---
title: Ottieni l'interlinea dei caratteri
linktitle: Ottieni l'interlinea dei caratteri
second_title: Riferimento all'API Aspose.Words per .NET
description: In questo tutorial, scopri come ottenere l'interlinea dei caratteri in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/get-font-line-spacing/
---
In questo tutorial, ti spiegheremo come ottenere l'interlinea del carattere in un documento di Word utilizzando la libreria Aspose.Words per .NET. L'interlinea del carattere definisce lo spazio verticale tra le righe di testo. Ti guideremo passo dopo passo per aiutarti a comprendere e implementare il codice nel tuo progetto .NET.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Conoscenza operativa del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto

## Passaggio 1: crea un nuovo documento e un generatore di documenti
 Innanzitutto, creeremo un nuovo documento istanziando il file`Document` class e un generatore di documenti istanziando il file`DocumentBuilder` classe.

```csharp
// Crea un nuovo documento
Document doc = new Document();

// Crea un generatore di documenti
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: configura il carattere
 Successivamente, configureremo il carattere impostando il file`Name` proprietà del generatore di documenti.

```csharp
//Configura il carattere
builder.Font.Name = "Calibri";
```

## Passaggio 3: aggiungi testo al documento
Useremo ora il generatore di documenti per aggiungere testo formattato al documento.

```csharp
// Aggiungi testo al documento
builder. Writen("qText");
```

## Passaggio 4: ottieni l'interlinea dei caratteri
 Ora accederemo al file`Font` oggetto del primo paragrafo del documento e recuperare il valore del`LineSpacing` proprietà.

```csharp
// Ottieni l'interlinea del carattere
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Codice sorgente di esempio per ottenere l'interlinea dei caratteri utilizzando Aspose.Words per .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Conclusione
In questo tutorial, abbiamo visto come ottenere l'interlinea dei caratteri in un documento Word con Aspose.Words per .NET. L'interlinea dei caratteri è importante per controllare la spaziatura verticale tra le righe di testo. Sentiti libero di usare questa funzione per personalizzare l'aspetto del tuo testo nei tuoi documenti.
