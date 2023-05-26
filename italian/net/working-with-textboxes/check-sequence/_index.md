---
title: Controlla la sequenza
linktitle: Controlla la sequenza
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come controllare la sequenza di TextBox in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-textboxes/check-sequence/
---

## Passaggio 1: impostazione del documento e creazione di una forma TextBox

 Per iniziare, dobbiamo impostare il documento e creare una forma TextBox. Il codice seguente inizializza una nuova istanza di`Document` class e crea una forma di casella di testo:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Passaggio 2: controllo della sequenza TextBox

 Verificheremo ora la sequenza del TextBox utilizzando`if` condizioni. Il codice sorgente fornito contiene tre condizioni separate per controllare la posizione del TextBox rispetto alle forme precedenti e successive.

## Passaggio 3: controllo della testina di sequenza:

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

Se il TextBox ha una forma successiva (`Next`) ma nessuna forma precedente (`Previous`), ciò significa che è l'inizio della sequenza. Verrà visualizzato il messaggio "The head of the sequence".

## Passaggio 4: controllo della parte centrale della sequenza:

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

Se il TextBox ha sia una forma Next (`Next`) e una forma precedente (`Previous`), questo indica che si trova nel mezzo della sequenza. Verrà visualizzato il messaggio "La parte centrale della sequenza".

## Passo 5: Verifica della fine della sequenza:

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

Se il TextBox non ha una forma successiva (`Next`) ma ha una forma precedente (`Previous`), ciò significa che è la fine della sequenza. Verrà visualizzato il messaggio "La fine della sequenza".

### Esempio di codice sorgente per verificare la sequenza con Aspose.Words per .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}

if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}

if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```