---
title: Bestelde lijst
linktitle: Bestelde lijst
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een geordende lijst kunt maken met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/ordered-list/
---

In dit voorbeeld leggen we uit hoe u de geordende lijstfunctionaliteit kunt gebruiken met Aspose.Words voor .NET. Met de Bestellijst kunt u items op volgorde ordenen met nummers.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om een nieuw document te maken.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Het geordende lijstformaat toepassen

 We passen het geordende lijstformaat toe met behulp van de documentbuilder`ApplyBulletDefault`methode. We kunnen het nummeringsformaat ook aanpassen door naar de lijstniveaus te gaan en het gewenste formaat in te stellen.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Stap 3: Items aan de lijst toevoegen

 We kunnen items aan de lijst toevoegen met behulp van de documentgenerator`Writeln` methode.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Stap 4: Laat de lijst inspringen

 We kunnen de lijst laten inspringen met behulp van de documentgenerator`ListIndent` methode.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Stap 5: Het document opslaan

Ten slotte kunnen we het document in het gewenste formaat opslaan.

### Voorbeeldbroncode voor geordende lijst met Aspose.Words voor .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Gefeliciteerd! U hebt nu geleerd hoe u de geordende lijstfunctie kunt gebruiken met Aspose.Words voor .NET.


### Veelgestelde vragen

#### Vraag: Hoe maak ik een geordende lijst in Markdown?

A: Om een geordende lijst in Markdown te maken, begint u elk lijstitem met een nummer gevolgd door een punt (`1.`, `2.`, `3.`), gevolgd door een spatie.

#### Vraag: Kunnen we geordende lijsten nesten in Markdown?

A: Ja, het is mogelijk om geordende lijsten in Markdown te nesten door vier offset-spaties toe te voegen vóór elk genest lijstitem.

#### Vraag: Hoe kan ik de nummering van geordende lijsten aanpassen?

A: Bij standaard Markdown wordt automatisch een geordende lijstnummering gegenereerd. Met sommige Markdown-editors kunt u deze echter aanpassen met specifieke extensies.

#### Vraag: Ondersteunen geordende lijsten in Markdown inspringen?

A: Ja, geordende lijsten in Markdown ondersteunen inspringen. U kunt een verschuiving naar links toevoegen met behulp van spaties of tabs.

#### Vraag: Kunnen links of inline tekst worden toegevoegd aan lijstitems?

A: Ja, u kunt links of inline tekst toevoegen aan lijstitems met behulp van de juiste Markdown-syntaxis.