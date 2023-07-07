---
title: Inserisci campo autore
linktitle: Inserisci campo autore
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un campo AUTHOR nei tuoi documenti Word con Aspose.Words per .NET. Specifica il nome dell'autore per personalizzare i tuoi documenti.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-author-field/
---


Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "Inserisci un campo AUTHOR" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e del paragrafo

Iniziamo creando un nuovo documento e recuperando il primo paragrafo.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Passaggio 3: inserire il campo AUTORE

 Noi usiamo il`AppendField()` metodo per inserire un campo AUTORE nel paragrafo.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Quindi configuriamo i campi`AuthorName` property per specificare il nome dell'autore.

```csharp
field. AuthorName = "Test1";
```

 Infine, chiamiamo il`Update()` metodo per aggiornare il campo.

```csharp
field. Update();
```

### Esempio del codice sorgente per l'inserimento di un campo AUTHOR con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Inserisci il campo AUTORE.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

In questo esempio, abbiamo creato un nuovo documento, inserito un campo AUTHOR, configurato il nome dell'autore e salvato il documento con un nome file specificato.

Questo conclude la nostra guida sull'utilizzo della funzione "Inserisci campo AUTORE" con Aspose.Words per .NET.

### FAQ

#### D: Cos'è un campo autore in Aspose.Words?

R: Un campo autore in Aspose.Words è un campo speciale che inserisce e aggiorna automaticamente il nome dell'autore in un documento Word. Viene spesso utilizzato per indicare chi ha creato o modificato il documento.

#### D: Come aggiornare il campo autore in un documento Word con Aspose.Words?

R: Il campo dell'autore in un documento Word può essere aggiornato per riflettere il nome dell'autore corrente. Per questo, puoi utilizzare il metodo UpdateFields disponibile nella classe Document. Questo metodo aggiornerà tutti i campi nel documento, incluso il campo dell'autore.

#### D: È possibile personalizzare il formato del campo dell'autore in un documento Word?

R: Sì, è possibile personalizzare il formato del campo dell'autore in un documento Word. Per impostazione predefinita, il campo dell'autore mostra semplicemente il nome dell'autore. Tuttavia, è possibile aggiungere ulteriori informazioni come la data e l'ora della modifica utilizzando le opzioni di formattazione disponibili in Aspose.Words.

#### D: Il campo dell'autore è sensibile alle successive modifiche al nome dell'autore?

R: Sì, il campo dell'autore è sensibile alle successive modifiche al nome dell'autore. Se modifichi il nome dell'autore nelle proprietà del documento, il campo dell'autore si aggiornerà automaticamente con il nuovo nome durante l'aggiornamento dei campi del documento.