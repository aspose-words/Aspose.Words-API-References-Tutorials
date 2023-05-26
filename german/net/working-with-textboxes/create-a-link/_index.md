---
title: Erstellen Sie einen Link
linktitle: Erstellen Sie einen Link
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Verknüpfung zwischen Textfeldern in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/working-with-textboxes/create-a-link/
---

## Schritt 1: Einrichten des Dokuments und Erstellen von TextBox-Formen

 Zunächst müssen wir das Dokument einrichten und zwei TextBox-Formen erstellen. Der folgende Code initialisiert eine neue Instanz von`Document` Klasse und erstellt zwei Textfeldformen:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## Schritt 2: Erstellen einer Verknüpfung zwischen TextBoxen

 Wir erstellen nun mithilfe von eine Verknüpfung zwischen den beiden TextBoxen`IsValidLinkTarget()` Methode und die`Next` Eigenschaft der ersten TextBox.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

 Der`IsValidLinkTarget()` Die Methode prüft, ob die zweite TextBox ein gültiges Ziel für den Link der ersten TextBox sein kann. Wenn die Validierung erfolgreich ist, wird die`Next` Die Eigenschaft der ersten TextBox wird auf die zweite TextBox gesetzt, wodurch eine Verknüpfung zwischen beiden erstellt wird.

### Beispielquellcode zur Verknüpfung mit Aspose.Words für .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```