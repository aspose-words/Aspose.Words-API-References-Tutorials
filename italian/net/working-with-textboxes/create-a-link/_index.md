---
title: Crea un collegamento
linktitle: Crea un collegamento
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare un collegamento tra le caselle di testo in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-textboxes/create-a-link/
---

## Passaggio 1: impostazione del documento e creazione di forme TextBox

 Per iniziare, dobbiamo impostare il documento e creare due forme TextBox. Il codice seguente inizializza una nuova istanza di`Document` class e crea due forme di caselle di testo:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## Passaggio 2: creazione di un collegamento tra le caselle di testo

 Ora creeremo un collegamento tra i due TextBox utilizzando il`IsValidLinkTarget()` metodo e il`Next` proprietà del primo TextBox.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

 IL`IsValidLinkTarget()` Il metodo controlla se il secondo TextBox può essere una destinazione valida per il collegamento del primo TextBox. Se la convalida ha esito positivo, il`Next` La proprietà del primo TextBox è impostata sul secondo TextBox, creando un collegamento tra i due.

### Esempio di codice sorgente da collegare con Aspose.Words per .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```