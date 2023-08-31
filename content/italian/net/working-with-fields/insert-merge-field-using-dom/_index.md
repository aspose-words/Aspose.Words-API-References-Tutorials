---
title: Inserisci campo unione utilizzando DOM
linktitle: Inserisci campo unione utilizzando DOM
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire campi di unione di campi personalizzati nei tuoi documenti Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/insert-merge-field-using-dom/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito che utilizza la funzionalità "Inserisci campo unione campo" di Aspose.Words per .NET. Assicurati di seguire attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "LA TUA DIRECTORY DOCUMENTI" con il percorso appropriato della directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e di DocumentBuilder

Iniziamo creando un nuovo documento e inizializzando un DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: spostare il cursore sul paragrafo

 Noi usiamo il`MoveTo()` del DocumentBuilder per spostare il cursore sul paragrafo in cui vogliamo inserire il campo unione campi.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Passaggio 4: inserimento del campo unione campi

 Usiamo DocumentBuilder`InsertField()` metodo per inserire un campo unione campi nel paragrafo.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Configuriamo quindi le proprietà del campo di unione dei campi specificando le opzioni appropriate, come il nome del campo, il testo prima e dopo il campo e le opzioni di formattazione verticale.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Infine, chiamiamo il`Update()` metodo per aggiornare il campo.

```csharp
field. Update();
```

### Codice sorgente di esempio per l'inserimento di un campo di unione di campi con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sposta il cursore sul paragrafo.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Inserisci campo unione campo.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Aggiorna il campo.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

In questo esempio, abbiamo creato un nuovo documento, spostato il cursore sul paragrafo desiderato e quindi inserito un campo di unione campi nel documento.

### Domande frequenti

#### D: Come posso inserire un campo di unione in un documento di Word utilizzando Aspose.Words per .NET con il DOM?

R: Per inserire un campo di unione in un documento di Word utilizzando Aspose.Words per .NET con DOM, puoi seguire questi passaggi:

1. Passare al paragrafo in cui si desidera inserire il campo di unione.
2.  Creare un`FieldMergeField` oggetto.
3. Imposta le proprietà del campo di unione, come il nome del campo e le opzioni di formattazione.
4.  Aggiungi il campo di unione al paragrafo utilizzando il comando`Paragraph.AppendChild` metodo.

#### D: Come posso specificare i dati di origine per il campo unione in Aspose.Words per .NET?

R: Per specificare i dati di origine per il campo di unione in Aspose.Words per .NET, è possibile utilizzare il file`FieldMergeField.FieldName` metodo per impostare il nome del campo di unione, che è il nome di un campo in un'origine dati esterna come un file CSV, un database, ecc. Puoi anche utilizzare il`FieldMergeField.Text` metodo per impostare direttamente il valore del campo di unione.

#### D: Posso personalizzare l'aspetto del campo unione in un documento di Word con Aspose.Words per .NET?

 R: Sì, puoi personalizzare l'aspetto del campo di unione in un documento di Word con Aspose.Words per .NET. Puoi impostare le opzioni di formattazione come maiuscole e minuscole, carattere, colore, ecc. utilizzando le proprietà del file`FieldMergeField` oggetto.

#### D: Come posso verificare se un campo unione è stato inserito correttamente in un documento Word con Aspose.Words per .NET?

 R: Per verificare se un campo unione è stato inserito correttamente, puoi sfogliare il contenuto del documento e cercare istanze di campi unione. È possibile utilizzare i metodi e le proprietà di`Document` oggetto per accedere a paragrafi, campi e altri elementi del documento.

#### D: L'inserimento di un campo di unione utilizzando DOM influisce sulla struttura del documento Word con Aspose.Words per .NET?

R: L'inserimento di un campo unione utilizzando il DOM non influisce direttamente sulla struttura del documento Word. Tuttavia, aggiunge un nuovo elemento campo al contenuto del documento. Puoi manipolare la struttura del documento aggiungendo, eliminando o modificando gli elementi esistenti in base alle tue esigenze.