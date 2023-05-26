---
title: Aggiungi commenti
linktitle: Aggiungi commenti
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come aggiungere commenti ai documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-comments/add-comments/
---

In questo tutorial completo imparerai come aggiungere commenti a un documento di Word usando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di inserire commenti e personalizzarne il contenuto nei tuoi documenti.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: aggiungere contenuto al documento
Successivamente, aggiungi il contenuto desiderato al documento utilizzando l'oggetto DocumentBuilder. In questo esempio, aggiungiamo del testo:

```csharp
builder.Write("Some text is added.");
```

## Passaggio 3: creare un commento e aggiungere contenuti
Per aggiungere un commento, crea un'istanza della classe Comment, passando l'oggetto Document, il nome dell'autore, le iniziali dell'autore e la data corrente:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Successivamente, aggiungi il commento al paragrafo corrente:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Aggiungi contenuti al commento, ad esempio un paragrafo e del testo:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Passaggio 4: salvare il documento
Dopo aver aggiunto il commento e il suo contenuto, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Esempio di codice sorgente per aggiungere commenti utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'aggiunta di commenti utilizzando Aspose.Words per .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Conclusione
Congratulazioni! Hai imparato con successo come aggiungere commenti a un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi inserire commenti e personalizzarne il contenuto nei tuoi documenti.

I commenti sono utili per la collaborazione, per fornire informazioni aggiuntive o per prendere appunti all'interno di un documento. Sperimenta con diversi nomi di autori, iniziali e contenuti dei commenti per soddisfare i tuoi requisiti specifici.