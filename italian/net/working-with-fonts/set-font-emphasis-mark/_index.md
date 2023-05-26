---
title: Imposta il segno di enfasi del carattere
linktitle: Imposta il segno di enfasi del carattere
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare lo stile di enfasi del carattere in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fonts/set-font-emphasis-mark/
---

In questo tutorial, ti mostreremo come impostare lo stile di enfasi del carattere in un documento Word usando Aspose.Words per .NET. L'enfasi del carattere viene utilizzata per evidenziare determinate parole o frasi nel testo.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti elementi:
- Conoscenza operativa del linguaggio di programmazione C#
- La libreria Aspose.Words per .NET installata nel tuo progetto

## Passaggio 1: definire la directory dei documenti
Inizia impostando il percorso della directory nella posizione del documento di Word. Sostituire`"YOUR DOCUMENT DIRECTORY"` nel codice con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creare e personalizzare il documento
 Crea un'istanza di`Document` classe e un associato`DocumentBuilder` per costruire il contenuto del documento. Usa il`Font.EmphasisMark`proprietà su cui impostare lo stile di enfasi del carattere`EmphasisMark.UnderSolidCircle` . Quindi usa il`Write` E`Writeln` metodi del`DocumentBuilder` per aggiungere testo con l'enfasi del carattere specificata.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Passaggio 3: salvare il documento
 Salvare il documento utilizzando il file`Save` metodo del`Document` con il percorso e il nome file appropriati.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Esempio di codice sorgente per Set Font Enphasis Mark utilizzando Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Conclusione
In questo tutorial, hai imparato come impostare lo stile di enfasi del carattere in un documento di Word usando Aspose.Words per .NET. Sperimenta con diversi stili di enfasi e usa questa funzione per evidenziare parole o frasi nei tuoi documenti.
