---
title: Ancora verticale
linktitle: Ancora verticale
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come posizionare verticalmente una forma all'interno di un documento utilizzando la funzione di ancoraggio verticale in Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-shapes/vertical-anchor/
---

Questo tutorial spiega come utilizzare la funzione di ancoraggio verticale in Aspose.Words per .NET per posizionare verticalmente una forma all'interno di un documento. Impostando la proprietà di ancoraggio verticale di una forma, puoi controllarne l'allineamento verticale rispetto al testo o alla pagina.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e lavoro con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"`con il percorso effettivo della directory in cui si desidera salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un nuovo documento e DocumentBuilder
 Crea una nuova istanza di`Document` classe e a`DocumentBuilder` opporsi a lavorare con il documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire e configurare una forma
 Inserisci una forma nel documento usando il`InsertShape` metodo del`DocumentBuilder` oggetto. Impostare le dimensioni desiderate per la forma.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Passaggio 4: impostare l'ancora verticale
Impostare la proprietà di ancoraggio verticale della forma per controllarne l'allineamento verticale. In questo esempio, lo impostiamo su "Bottom" per ancorare la forma nella parte inferiore del testo o della pagina.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Passaggio 5: aggiungere contenuto alla forma
 Usa il`MoveTo` metodo del`DocumentBuilder` oggetto per spostare il cursore sul primo paragrafo della forma. Quindi, usa il`Write` metodo per aggiungere contenuto alla forma.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Passaggio 6: salvare il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Codice sorgente di esempio per l'ancoraggio verticale utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Questo è tutto! Hai utilizzato con successo la funzione di ancoraggio verticale in Aspose.Words per .NET per posizionare verticalmente una forma all'interno di un documento.