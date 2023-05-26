---
title: Kontrollera Sekvens
linktitle: Kontrollera Sekvens
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du kontrollerar sekvensen av textrutor i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-textboxes/check-sequence/
---

## Steg 1: Konfigurera dokumentet och skapa en TextBox-form

 För att börja måste vi ställa in dokumentet och skapa en TextBox-form. Följande kod initierar en ny instans av`Document` klass och skapar en textrutaform:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Steg 2: Kontrollera TextBox-sekvensen

 Vi kommer nu att kontrollera sekvensen av TextBox med hjälp av`if` betingelser. Den tillhandahållna källkoden innehåller tre separata villkor för att kontrollera textrutans position i förhållande till de föregående och följande formerna.

## Steg 3: Kontrollera sekvenshuvudet:

```csharp
if (textBox. Next != null && textBox. Previous == null)
{
     Console.WriteLine("The head of the sequence");
}
```

Om textrutan har en nästa form (`Next`) men ingen tidigare form (`Previous`), det betyder att det är sekvensens huvud. Meddelandet "Sekvensens huvud" kommer att visas.

## Steg 4: Kontrollera mitten av sekvensen:

```csharp
if (textBox. Next != null && textBox. Previous != null)
{
     Console.WriteLine("The middle of the sequence.");
}
```

Om textrutan har både en Nästa form (`Next`) och en tidigare form (`Previous`), detta indikerar att det är mitt i sekvensen. Meddelandet "Mitt i sekvensen" kommer att visas.

## Steg 5: Verifiering av slutet av sekvensen:

```csharp
if (textBox. Next == null && textBox. Previous != null)
{
     Console.WriteLine("The end of the sequence.");
}
```

Om textrutan inte har någon nästa form (`Next`) men har en tidigare form (`Previous`), det betyder att det är slutet på sekvensen. Meddelandet "Slutet på sekvensen" kommer att visas.

### Exempel på källkod för att verifiera sekvens med Aspose.Words för .NET

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