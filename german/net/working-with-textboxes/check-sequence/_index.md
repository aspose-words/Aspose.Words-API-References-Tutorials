---
title: Reihenfolge prüfen
linktitle: Reihenfolge prüfen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Reihenfolge von Textfeldern in einem Word-Dokument überprüfen.
type: docs
weight: 10
url: /de/net/working-with-textboxes/check-sequence/
---

## Schritt 1: Einrichten des Dokuments und Erstellen einer TextBox-Form

 Zunächst müssen wir das Dokument einrichten und eine TextBox-Form erstellen. Der folgende Code initialisiert eine neue Instanz von`Document` Klasse und erstellt eine Textfeldform:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Schritt 2: Überprüfen der TextBox-Sequenz

 Wir werden nun die Reihenfolge der TextBox mit überprüfen`if` Bedingungen. Der bereitgestellte Quellcode enthält drei separate Bedingungen, um die Position der TextBox relativ zu den vorhergehenden und folgenden Formen zu überprüfen.

## Schritt 3: Überprüfung des Sequenzkopfes:

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

Wenn die TextBox eine nächste Form hat (`Next`), aber keine vorherige Form (`Previous`), das heißt, es ist der Kopf der Sequenz. Die Meldung „Der Kopf der Sequenz“ wird angezeigt.

## Schritt 4: Überprüfung der Mitte der Sequenz:

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

Wenn die TextBox sowohl eine Next-Form (`Next`) und eine vorherige Form (`Previous`), zeigt dies an, dass es sich in der Mitte der Sequenz befindet. Die Meldung „Die Mitte der Sequenz“ wird angezeigt.

## Schritt 5: Überprüfung des Endes der Sequenz:

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

Wenn die TextBox keine nächste Form hat (`Next`), hat aber eine frühere Form (`Previous`), das heißt, es ist das Ende der Sequenz. Die Meldung „Das Ende der Sequenz“ wird angezeigt.

### Beispielquellcode zur Überprüfung der Sequenz mit Aspose.Words für .NET

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